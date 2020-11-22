<template>
  <div>
    <el-container class="header-wrapper">
      <el-main>
        <el-row>
          <el-col :span="12" :offset="6">
            <el-row>
              <el-col :xs="24" :sm="24" :md="24" :lg="24" :xl="24">
                <div class="header">
                  <div class="user-name">
                    <h1>Todo List</h1>
                  </div>
                  <div class="date-wrapper">
                    <span class="day">Sunday,</span
                    ><span class="date">12th</span
                    ><span class="month">March</span>
                  </div>
                  <!-- <div class="trash-bin">
                    <el-popover
                      placement="top-start"
                      width="60"
                      trigger="hover"
                      content="Goto Trash"
                    >
                      <el-button slot="reference" icon="el-icon-delete" type="info" circle></el-button>
                    </el-popover>
                  </div> -->
                </div>
              </el-col>
            </el-row>
          </el-col>
        </el-row>
      </el-main>
    </el-container>
  </div>
</template>

<style>
</style>

<script>
</script>
