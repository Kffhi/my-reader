<template>
<div class="ebook">
    <div class="read-wrapper">
        <div id="read"></div>
    </div>
</div>
</template>

<script>
    import Epub from 'epubjs'
    const DOWNLOAD_URL = '/2018_Book_AgileProcessesInSoftwareEngine.epub'
    global.ePub = Epub
    export default {
        name: "Ebook",
        methods: {
            // 电子书的解析和渲染
            showEpub() {
                // 生成Book
                this.book = new Epub(DOWNLOAD_URL)
                // console.log(this.book)
                // 生成Rendition，通过Book.renderTo
                this.rendition = this.book.renderTo('read', {
                    width: window.innerWidth,
                    height: window.innerHeight
                })
                // 通过Rendtion.display渲染电子书
                this.rendition.display()
            }
        },
        mounted() {
            this.showEpub()
        }
    }
</script>

<style lang="scss" scoped>
@import "./assets/styles/global";
</style>
