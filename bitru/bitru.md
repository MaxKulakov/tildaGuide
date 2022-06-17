# Bitru
## Header background blur
```bash
<style>
    .t228__maincontainer {
        backdrop-filter: blur(4px);
        -webkit-backdrop-filter: blur(4px);
    }

    .t280__menu__bg, .t280__menu__content  {
        background-color: transparent !important;
        backdrop-filter: blur(20px);
        -webkit-backdrop-filter: blur(20px);
    }

    .t280__menu__item{
        font-size: 32px;
    }
</style>
```

## Card scroll
```bash
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/OwlCarousel2/2.3.4/assets/owl.carousel.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/OwlCarousel2/2.3.4/assets/owl.theme.default.min.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/OwlCarousel2/2.3.4/owl.carousel.min.js"></script>

<script>
(function () {
	// ID slider block
	let block = $("#rec456836874");
	// ID shape in block
	let wrap = $(".tn-elem__4568368741654782064227");
	// ID slides
	let slides = $("#rec456837001, #rec457067559");

	wrap.addClass("tildoshnaya-slider-owl");
	let box = wrap.find(".tn-atom");
	box.append('<div class="owl-carousel owl-theme"></div>');
	slides.appendTo(block.find('.owl-carousel'));
	let owl = wrap.find('.owl-carousel').owlCarousel({
	    loop:true,
	    nav:false,
	    dots: false,
	    items: 1,

	    responsive:{
	        0:{
	            items:1
	        },
	        640:{
	            items:1
	        },
	        960:{
	            items:1
	        },
	    }
	})


	block.find("[href='#slider_left']").click(function(){
		owl.trigger('prev.owl.carousel');
	})
	block.find("[href='#slider_right']").click(function(){
		owl.trigger('next.owl.carousel');
	})
}());
</script>


<script>
function auto_play() {  $("[href='#slider_right']").click()};
var timemode = 8000; /* Slider speed */
var autoPlay = setInterval( auto_play, timemode );
</script>


<style>
    .slider_left:hover, .slider_right:hover{
        border-radius: 60px;
        box-shadow: 0px 4px 100px rgba(61, 204, 106, 0.35);
    }
</style>
```

## Border card item
```bash
<style>
    .catalog_card .tn-atom {
        border-radius: 40px 0px;
    }
</style>
```

## Card horizontal scroll
```bash
<!-- scroll catalog-->
<script src="https://unpkg.com/scrollbooster@3/dist/scrollbooster.min.js" defer></script>

<script>
$(function() {
    var blockScrollId = '#rec456620456';
    var blockArrowsId = '#rec456618796';

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

.arrow-left:hover, .arrow-right:hover{
    border-radius: 60px;
    box-shadow: 0px 4px 100px rgba(61, 204, 106, 0.35);
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

.t-popup__close{
    display: none;
}

</style>

<script>
var ZeroPopID = '#rec456871006'; // ID Zero PopUp Design
var PopWindID = '#rec456866903'; // ID PopUp BF503
$(PopWindID + " .t-popup__container").addClass("shirina").html($(ZeroPopID));
$(PopWindID + " .t-popup__container").parent(".t-popup").addClass("parpadding")
</script>
```

## Button hover in native contact block

```bash
<style>
    .tn-form__submit .t-submit:hover {
        background-color: #2B7444 !important;
        transition: background-color 0.2s ease-in-out;
    }
</style>
```
