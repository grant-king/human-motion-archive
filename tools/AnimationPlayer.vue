<template>
    <div class="hidden">
        <img :width="ASSET_SIZE" :height="ASSET_SIZE" ref="el_img_asset_source" :src="props.asset_url"
            crossorigin="anonymous" />
    </div>
    <canvas @click="handle_player_click()"
        class="w-full aspect-square bg-[url(https://sagaymedia.blob.core.windows.net/default/openmoji/color/25B6.svg)]"
        ref="el_canvas_display">
    </canvas>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

const FRAME_SIZE = 64
const ASSET_SIZE = 1024

const is_playing = ref(false)
const current_frame_source_x = ref(0)
const current_frame_source_y = ref(0)
const last_timestamp_play_loop = ref(0)

const el_img_asset_source = ref(null)
const el_canvas_display = ref(null)

onMounted(() => {
    draw_next_frame()
})

onBeforeUnmount(() => {
    is_playing.value = false
})

const props = defineProps({
    asset_url: {
        type: String,
        required: true
    },
    fps: {
        type: Number,
        required: false,
        default: 12
    }
})

function handle_player_click() {
    if (!is_playing.value) {
        play_animation()
    } else {
        pause_animation()
    }
}

function play_animation() {
    is_playing.value = true
    requestAnimationFrame(raf_callback_play_loop)
}

function pause_animation() {
    is_playing.value = false
}

function raf_callback_play_loop(timestamp) {
    if (timestamp - last_timestamp_play_loop.value >= (1000 / props.fps)) {
        last_timestamp_play_loop.value = timestamp
        draw_next_frame()
        update_frame_source_positions()
    }
    if (is_playing.value) {
        requestAnimationFrame(raf_callback_play_loop)
    }
}

function draw_next_frame() {
    // draw next frame at current source locs over canvas
    const display_ctx = el_canvas_display.value.getContext('2d')
    display_ctx.imageSmoothingEnabled = false
    display_ctx.drawImage(
        el_img_asset_source.value,
        current_frame_source_x.value, current_frame_source_y.value, // source start x, y
        FRAME_SIZE, FRAME_SIZE, // source size
        0, 0, // destination draw start x, y
        el_canvas_display.value.width, el_canvas_display.value.height // destination size
    )
}

function update_frame_source_positions() {
    current_frame_source_x.value = (current_frame_source_x.value + FRAME_SIZE) % ASSET_SIZE
    if (current_frame_source_x.value === 0) {
        current_frame_source_y.value = (current_frame_source_y.value + FRAME_SIZE) % ASSET_SIZE
    }
}

</script>