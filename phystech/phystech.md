# Phystech

## Card scroll
![Card scroll](images/card_scroll.png?raw=true "Title")
```bash
<!-- scroll first-rooms-->
<script src="https://unpkg.com/scrollbooster@3/dist/scrollbooster.min.js" defer></script>

<script>
$(function() {
    var blockScrollId = '#rec449037202';
    var blockArrowsId = '#rec456178460';

    var shiftSize;
    $(window).on('load resize', function(){

        if (window.matchMedia('(max-width: 480px)').matches) {
            shiftSize = '320px';
        }
        else if (window.matchMedia('(max-width: 640px)').matches) {
            shiftSize = '320px';
        }
        else if (window.matchMedia('(max-width: 960px)').matches) {
            shiftSize = '320px';
        }
        else if (window.matchMedia('(max-width: 1200px)').matches) {
            shiftSize = '320px';
        }
        else {
            shiftSize = '400px';
        }

    });


    $(blockScrollId + ' .t396__artboard').addClass('scrollbooster-viewport').wrapInner('<div class="scrollbooster-content"></div>');
    $(blockScrollId + ' .t396').css('overflow','hidden');

    new ScrollBooster({
        viewport: $(blockScrollId + ' .scrollbooster-viewport')[0],
        content:  $(blockScrollId + ' .scrollbooster-content')[0],
        scrollMode: 'native',
        pointerMode: 'mouse',
        bounce: false,
        onPointerDown: function() { $(blockScrollId + ' *:focus').blur() }
    });

    $(blockArrowsId + ' .arrow-left').on('click', function(e) {
        e.preventDefault();
        $(blockScrollId + ' .t396__artboard').animate( { scrollLeft: '-=' + shiftSize }, 300);
    });

    $(blockArrowsId + ' .arrow-right').on('click', function(e) {
        e.preventDefault();
        $(blockScrollId + ' .t396__artboard').animate( { scrollLeft: '+=' + shiftSize }, 300);
    });

});
</script>

<style>
.scrollbooster-viewport {
    cursor: -webkit-grab;
    cursor: grab;
    padding-bottom: 30px;
    margin-bottom: -30px;
}
.scrollbooster-viewport:active {
    cursor: -webkit-grabbing;
    cursor: grabbing;
}
.scrollbooster-content {
    position: absolute;
    width: 100%;
    height: 100%;
}
.arrow-left,
.arrow-right {
    cursor: pointer;
}
</style>
```

## Hover img zoom
```bash
<!-- Zoom images on Benefits and News -->

<style>
.t396__elem.zoomon {
border-radius: 8px;
overflow: hidden;
}

.zoomon .tn-atom {
border-radius: 8px;
transition: all 0.5s ease;
}

.zoomon .tn-atom:hover {
border-radius: 8px;
transform: scale(1.1);
}
</style>
```

## Custom PopUp
```bash
<!-- Pop-up on benefits and News -->

<style>

.shirina{
background:none !important;
right: 0 !important;
left: 0 !important;
}

.parpadding{
padding:0 !important;
}

</style>

<script>
var ZeroPopID = '#rec445865881'; // ID Zero PopUp Design
var PopWindID = '#rec456378057'; // ID PopUp BF503
$(PopWindID + " .t-popup__container").addClass("shirina").html($(ZeroPopID));
$(PopWindID + " .t-popup__container").parent(".t-popup").addClass("parpadding")
</script>
```

## Dropdown block
```bash
<!--show all docs-->
<style>
    #rec451245906  {
        display:none;
}
</style>

<script>
    $('[href = "#doc-full-list"]').click(function() {
        $('#rec451245906').slideToggle(500); t_lazyload_update();
    });
</script>
```

## Crop large text
```bash
<style>
    /*.doc-background:hover{*/
    /*    background-color: #FF0000;*/
    /*    background-opacity: 0.15;*/
    /*}*/

    @media (max-width: 480px) {
        .doc-name {
            max-width: 248px;
            width: 248px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        .doc-name .tn-atom {
            max-width: 248px;
            width: 248px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
    }
    @media (min-width: 481px) {
        .doc-name {
            max-width: 398px;
            width: 398px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        .doc-name .tn-atom {
            max-width: 398px;
            width: 398px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
    }
    @media (min-width: 640px) {
        .doc-name {
            max-width: 558px;
            width: 558px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        .doc-name .tn-atom {
            max-width: 558px;
            width: 558px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
    }
    @media (min-width: 960px) {
        .doc-name {
            max-width: 398px;
            width: 398px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        .doc-name .tn-atom {
            max-width: 398px;
            width: 398px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
    }
    @media (min-width: 1200px) {
        .doc-name {
            max-width: 498px;
            width: 498px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        .doc-name .tn-atom {
            max-width: 498px;
            width: 498px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
    }
</style>
```
