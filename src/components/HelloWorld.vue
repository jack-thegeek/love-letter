<script setup>
import '@varlet/touch-emulator'
import {Snackbar} from '@varlet/ui'
import '@varlet/ui/es/snackbar/style/index.js'

  const handleClick = () => {
    Snackbar.success('点击成功')
}

const handleTouchstart = () => {
    Snackbar.success('触摸成功')
}

// const handleAutoLoadingClick = () => {
//   return new Promise((resolve) => {
//     setTimeout(resolve, 2000)
//   })
// }

const handleAutoLoadingClick = async () => {
    const result1 = await new Promise((resolve) => {
        setTimeout(() => resolve('1'), 2000)
    })
}

</script>

<template>
	<var-space :size="[10, 10]">
		<var-button type="success" @click="handleClick">点击</var-button>
		<var-button type="success" @touchstart="handleTouchstart">触摸</var-button>
		<var-button
				type="success"
				auto-loading
				@click="handleAutoLoadingClick"
		>
			自动 loading
		</var-button>
	</var-space>
</template>
