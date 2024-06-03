<template>
  <el-button plain @click="dialogVisible = true"> Click to open the Dialog </el-button>

  <el-dialog v-model="dialogVisible" title="Tips" width="500" :before-close="handleClose">
    <span>This is a message</span>
    <div>
      <video id="video1" style="width: 600px; max-width: 100%" controls="">
        <!-- <source src="../assets/mov_bbb.mp4" type="video/mp4" /> -->
        <source src="https://www.w3schools.com/html/mov_bbb.mp4" type="video/mp4" />

        Your browser does not support HTML5 video.
      </video>
    </div>
    <template #footer>
      <div class="dialog-footer">
        <el-button @click="dialogVisible = false">Cancel</el-button>
        <el-button type="primary" @click="dialogVisible = false"> Confirm </el-button>
      </div>
    </template>
  </el-dialog>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import { ElMessageBox } from 'element-plus'

const dialogVisible = ref(false)

const handleClose = (done: () => void) => {
  ElMessageBox.confirm('Are you sure to close this dialog?')
    .then(() => {
      done()
    })
    .catch(() => {
      // catch error
    })
}
</script>
