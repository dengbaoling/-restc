### Color

#### Random.color()

* Random.color()

随机生成一个颜色，格式为 '#RRGGBB'。

**使用示例**如下所示：

    Random.color()
    // => "#3538B2"

下面是一些随机生成的颜色：

<button id="genColor" type="button" class="btn btn-default">重新生成一批</button>

<div id="color100" class="color_100"></div>
<style type="text/css">
    .circle {
        display: inline-block;
        width: 5em;
        height: 5em;
        border-radius: 50%;
        margin: 0 1em 1em 0;
        line-height: 5em;
        vertical-align: middle;
        text-align: center;
        color: #FFF;
    }
</style>
<script>
    $(function(){
        $('#genColor').on('click', function(event){
            var container = $('#color100').empty()
            var color
            for (var i = 0; i < 35; i++) {
                color = Random.color()
                $('<span class="circle"></span>')
                    .css('background-color', color)
                    .appendTo(container)
            }      
        }).trigger('click')
    })
</script>
