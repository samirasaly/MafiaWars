<template>
    <div class="overlay">
        <div class="inner-overlay">
            <div class="overlay-box">
                <div class="inner-overlay-box">
                    <slot></slot>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style lang="scss" scoped>

.overlay {
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	overflow-y: auto;
	visibility: hidden;
	opacity: 0;
	background: $transparent_black;
	z-index: 999999;
    transition: all .2s ease-in-out;
    .inner-overlay {
        display: table;
        width: 100%;
        height: 100%;
        .overlay-box {
            display: table-cell;
            vertical-align: middle;
            font-size: $font_size_4;
            text-align: center;
            padding: 20px;
            .inner-overlay-box {
                position: relative;
                max-width: 780px;
                margin: auto;
                border-radius: 2px;
            }
        }
    }
    &.active{
        visibility: visible;
	    opacity: 1;
    }
    &.dialog{
        top:1%;
        left:1%;
        width: 98%;
        height: 98%;
        overflow-y: hidden;
        border-radius: 6px;
        background:rgba(0, 0, 0, 0.97);
    }
    &.log{
        position: absolute;
        top: 50%;
        left: 50%;
        width: 320px;
        height: 320px;
        margin: -160px 0 0 -160px;
        overflow-y: hidden;
        border:4px solid $black_color;
        border-radius: 50%;
        background: rgba(7, 7, 7, 0.99);
        transform: scale(0, 0);
        transition:all .4s;
        .overlay-box{
            font-size: $font_size_6;
            img{
                padding:10px;
                border:2px solid $background_color_1;
                border-radius: 50%;
            }
        }
        &::after{
            content:'';
            position: absolute;
            top: 3px;
            left: 3px;
            width: calc(100% - 6px);
            height: calc(100% - 6px);
            border:4px solid $black_color;
            border-radius: 50%;
        }
        &.active{
            transform:scale(1,1);
        }
        &.done{
            transform:scale(.3,.3);
        }
    }
    &.last-night{
        h2{
            font-family: $font_mafia;
            font-size: 38px;
            color: $color_site_2;
            margin-top: 15px;
            margin-bottom: 22px;
        }
        ul{
            li{
                margin-bottom: 10px;
                
            }
        }
        a.bttn{
            margin-top:30px;
        }
    }
}

</style>

