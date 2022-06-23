# Bitru
[View BitRu Site](http://bitru.pro/)  
## Header background blur
![Header background blur](images/header_blur.png?raw=true "Header background blur")

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

## Screen scroll
![Screen scroll](images/screen_scroll.png?raw=true "Screen scroll")
```bash
<style>
.t734 { height: auto !important; }
.t734 .t-slds__arrow_container {display: none}
</style>
<script>
$(document).ready(function(){
let sldID = ['#rec461246126'];
setTimeout(function(){
for (let i=0; i<sldID.length; i++){
    let sliderEl = sldID[i]+' .t-slds__item';
    let slidercount = $(sliderEl).length; $(sliderEl).empty(); let start=0;
    if(!$(sliderEl+'[data-slide-index="0"]').length){start=1};
    for (let j=0; j<slidercount; j++){
        let sInd = j+start;
        if(start){ slideId = '#'+$(sldID[i]).next().next('div[data-record-type="396"]').attr('id');
        }else{ slideId = '#'+$(sldID[i]).next('div[data-record-type="396"]').attr('id')
        if(j==0){sInd=slidercount-1};if(j==slidercount-1){sInd=0};
        }; $(slideId).appendTo(sliderEl+'[data-slide-index='+(sInd)+']');
    };  if(start){ $(sldID[i]).next().hide(); $(sldID[i]).next().next().hide()};
};
}, 100);  

//Управляем слайдером своими стрелками из Zero
//При клике на левую кнопку - крутим слайдер влево
 $("a[href = '#leftsld']").click(function(event) {
   $(".t734 .t-slds__arrow-left")[0].click();
   event.preventDefault();
  });
//При клике на правую кнопку - крутим слайдер вправо
  $("a[href = '#rightsld']").click(function(event) {
   $(".t734 .t-slds__arrow-right")[0].click();
   event.preventDefault();
  });    
  $(document).keydown(function(e){
if (e.which == 37) {
     $(".t734 .t-slds__arrow-left")[0].click();
    };  
if (e.which == 39) {
     $(".t734 .t-slds__arrow-right")[0].click();
    };      
 })
});    

</script>
```

## Border card item
![Border card item](images/card_scroll.png?raw=true "Border card item")
```bash
<style>
    .catalog_card .tn-atom {
        border-radius: 40px 0px;
    }
</style>
```

## Card horizontal scroll
![Card horizontal scroll](images/card_scroll.png?raw=true "Card horizontal scroll")
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
![Custom PopUp](images/custom_popup.png?raw=true "Custom PopUp")

```bash
<script>
document.addEventListener("DOMContentLoaded", function(){
//Полуаем нужные элементы
let popupBtn =  document.querySelectorAll('[href^="#uc-zw"]');
let popupZero = document.querySelectorAll('div[class*="uc-zw-"]');
let mainPopup = document.querySelector('.uc-main-popup');

if(popupBtn.length&&popupZero.length&&mainPopup){
    let popupCont = mainPopup.querySelector('.t-popup__container');
    let popupCloseIcon = mainPopup.querySelector('.t-popup__close');

    //Очищаем popup и получаем ссылку его вызова
    popupCont.innerHTML = '';
    let popupHook = mainPopup.querySelector('.t-popup').getAttribute('data-tooltip-hook');

    //Создаём элемент со ссылкой вызова popup
    let popupLink = document.createElement('a');
    popupLink.href = popupHook; popupLink.className = "bf503-zero";
    mainPopup.appendChild(popupLink);

    //Размечаем наши Zero для привязки к нужной ссылке
    for (let i = 0; i < popupZero.length; i++) {
        popupZero[i].classList.add("popup-zero" , "hide-popup-zero");

        //Закрываем окно при клике на вне элементов
        popupZero[i].querySelector('.t396__filter').addEventListener('click', function() { popupCloseIcon.click() });

        //Закрываем окно при клике на кнопку #popup-close
        setTimeout(function(){
            let closeIcon = popupZero[i].querySelector('a[href="#popup-close"]');
            if(closeIcon != null){
                popupCloseIcon.classList.add("hide-popup-zero");
                closeIcon.addEventListener('click', function(e) {
                    popupCloseIcon.click();e.preventDefault();
                });
            };
        }, 1000);

        //Закрываем окно при отправке формы
        popupZero[i].addEventListener('click', function(e){
            let type = e.target.getAttribute('type');
            if(type=="submit"){
                setTimeout(function(){
                    let form = e.target.closest('.t-form');
                    if (form.classList.contains('js-send-form-success')) popupCloseIcon.click();
                }, 1000);
            };
        });

        //Добавляем атрибут в виде ссылки
        let classZeroPopup = popupZero[i].getAttribute('class');
        let classArrZeroPopup = classZeroPopup.split(' ');
        classArrZeroPopup.forEach(function(item, j) {
            if(item.includes('uc-zw-')) {
                popupZero[i].setAttribute('data-zero-popup', item);
                popupZero[i].classList.remove(item);
            };
        });
    };


    const $back = document.querySelector('#rec456903634 > div > div > div.t396__elem.tn-elem.tn-elem__4569036341654791504341 > a')
    $back.addEventListener('click', function () {
            document.querySelector('#rec456904207 > div > div').click()
    })


    //Отслеживаем закрытие окна
    let popupShow = mainPopup.querySelector('.t-popup');
    let observer = new MutationObserver(function (mutations) {
        mutations.forEach(function (mutation) {
            setTimeout(function(){
                popupShow = mainPopup.querySelector('.t-popup');
                if (!popupShow.classList.contains('t-popup_show')) {
                    let activeZero = mainPopup.querySelector('.active-popup-zero');

                    let frame = activeZero.querySelectorAll('iframe');
                    if(frame.length){frame.forEach(i => i.src = i.src)};

                    let video = activeZero.querySelectorAll('video');
                    if(video.length){video.forEach(i => i.pause())};
                };
            }, 500);
        });
    });
    observer.observe( popupShow, {  attributes: true, attributeFilter: ['class'] });

    //Отслеживаем нажатие кнопок для вызова окна
    for (let i = 0; i < popupBtn.length; i++) {
        popupBtn[i].addEventListener('click', function(e) {e.preventDefault();
            let link = (this.getAttribute('href')).replace('#' , '');
            let popupZeroActive = document.querySelector('div[data-zero-popup="'+link+'"]');
            if(popupZeroActive){
                if (!popupZeroActive.hasAttribute("zero-popup-mode")) {
                    popupCont.append(popupZeroActive);
                    popupZeroActive.setAttribute('zero-popup-mode','');  
                };
                let zeroInside = popupCont.querySelectorAll('.popup-zero');
                if(zeroInside){
                    zeroInside.forEach(i => i.classList.add("hide-popup-zero"));
                    zeroInside.forEach(i => i.classList.remove("active-popup-zero"))
                };
                popupZeroActive.classList.remove('hide-popup-zero');
                popupZeroActive.classList.add('active-popup-zero');

                let popup = mainPopup.querySelector('.t-popup');
                popup.classList.add("popup-transition");
                popupLink.click();
            };
        });
    };
};
});
</script>

<style>
div[class*="uc-zw-"], .hide-popup-zero {
    opacity: 0!important;
    min-height: 0!important;
    max-height: 0!important;
    pointer-events: none!important;
    padding-top: 0 !important;
    padding-bottom: 0 !important;
    overflow: hidden !important;
}
.uc-main-popup .t-popup {
    padding: 0;
    display: block !important;
    pointer-events: none;
}
.uc-main-popup .t-popup__container {left:0; right:0;background: none}
.tn-atom .t-form__errorbox-wrapper,
.tn-form__errorbox-popup,
.t-form-success-popup { z-index: 9999999 !important}
div#tilda-popup-for-error {display: none !important}
.popup-zero .t396__filter {cursor: pointer}
.uc-main-popup .t-popup.t-popup_show {pointer-events: auto}
.uc-main-popup .t-popup { transition: none}
.uc-main-popup .popup-transition {transition: opacity ease-in-out .3s;}


</style>
```

## Button hover in native contact block
![Button hover](images/button_hover.png?raw=true "Button hover")
```bash
<style>
    .tn-form__submit .t-submit:hover {
        background-color: #2B7444 !important;
        transition: background-color 0.2s ease-in-out;
    }
</style>
```

## Change placeholder style
![Change placeholder style](images/custom_placeholder.png?raw=true "Change placeholder style")
```bash
<style>

    /*этот блок не трогай, он хороший и отвечает за ховер кнопки отправить*/
    .tn-form__submit .t-submit:hover {
        background-color: #2B7444 !important;
        transition: background-color 0.2s ease-in-out;
    }
    /*Всё ещё не трогай блок выше*/

    /* Change the white to any color */
input:-webkit-autofill,
input:-webkit-autofill:hover,
input:-webkit-autofill:focus,
input:-webkit-autofill:active{
    -webkit-box-shadow: 0 0 0 30px #252729 inset !important;
}

input:-webkit-autofill{
    -webkit-text-fill-color: white !important;
}


    input:focus, textarea:focus{
            border: 1px solid #3DCC6A !important;
    }

    .t-input ~ .t-input__vis-ph {
        top: 15px !important;
        font-weight: 400 !important;
        font-size: 16px !important;
        height: 16px !important;
        color: #5c5f66 !important;
        opacity: 1 !important;
        padding: 2px !important;
    }

    .t-input.t-input_has-content ~ .t-input__vis-ph {
        top: 10px !important;
        background: #191b1d !important;
    }


    .t-input:focus ~ .t-input__vis-ph {
        top: 10px !important;
        background: #191b1d !important;
        color: #3ecc69 !important;
    }

    .t-input-block {
        overflow: unset !important;
    }

    .tn-atom__form .t-input {
        padding: 10px 20px 10px 20px !important;
    }

    /*.tn-atom__form .t-input.t-input_has-content {*/
    /*    padding: 26px 20px 10px 20px !important;*/
    /*}*/

</style>

<script>
    // window.addEventListener('load', () => {
    //     setTimeout(() => {
    //         document.querySelectorAll('input').forEach($el => $el.setAttribute('autocomplete', 'off'))
    //     }, 250)

    // })
</script>
```


## Close form when submit
![Close form when submit](images/custom_popup.png?raw=true "Close form when submit")
```bash
<script>
    window.onload = function () {
        setTimeout(function () {
            const $form = document.querySelector('#form458869618')

            $form.addEventListener('tildaform:aftersuccess', function () {
                document.querySelector('#rec458869618 > div > div > div.t396__elem.tn-elem.tn-elem__4588696181655303021570 > a').click()
            })
        }, 500)
    };
</script>
```
