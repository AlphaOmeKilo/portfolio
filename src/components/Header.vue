<template>
    <header>
        <div id="nav" class="header uk-flex uk-flex-bottom uk-position-relative">
            <ul class="menu uk-flex" uk-sticky>
                <li><router-link to="/">Home</router-link></li>
                <li><router-link to="/about">About</router-link></li>
                <li>Work</li>
                <li>Contact</li>
                <li>Random</li>
                
            </ul>
        </div>
            <!-- <router-link to="/">Home</router-link> | -->
    </header>
</template>

<script>
import jQuery from 'jquery';

export default {
    name: 'Header'
}

var $ = jQuery.noConflict();

$.fn.reverse = [].reverse;

$(document).ready(function() {

    function idleLogout() {
        var t;
        resetTimer();
        window.onload = resetTimer;
        window.onmousemove = resetTimer;
        window.onmousedown = resetTimer;      
        window.ontouchstart = resetTimer; 
        window.onclick = resetTimer; 
        window.onkeypress = resetTimer;   
        window.addEventListener('scroll', resetTimer, true); 

        function yourFunction() {
            $('.menu').addClass('active');
            if ($('.menu').offset().top - $(window).scrollTop() > 20 ) {
                $('.menu li').reverse().each(function(index) {
                    index = index + 1;

                    $(this).css({'margin-left': 500*index + 'px'});

                });
            }
        }

        function resetTimer() {
            $('.menu').removeClass('active');
            $('.menu li').reverse().each(function() {
                $(this).css({'margin-left': '0px'});
            });

            clearTimeout(t);
            t = setTimeout(yourFunction, 10000); 
        }
    }
    idleLogout();


    $(window).on('scroll', function() {
        changeMenu();
    });

    var changeMenu = function() {
        $('.menu').each(function() {
            var topPosition = $(this).offset().top - $(window).scrollTop();
            if(topPosition <= 100) {
                topPosition = topPosition/10;
                $(this).css({'transform': 'rotate(' + topPosition + 'deg)'});
            } else {
                $(this).css({'transform': 'rotate(10deg)'});
            }
        });
    }

    changeMenu();
    
});
</script>

<style scoped>
.header-overflow {
    height: 200px;
    color: #000;
    -ms-transform: rotate(10deg);
    -webkit-transform: rotate(10deg);
    transform: rotate(10deg);
}

.header {
    background-color: #000;
    height: 130px;
    width: 140%;
    z-index: 100;
}

.menu {
    position: relative;
    list-style: none;
    -ms-transform: rotate(10deg);
    -webkit-transform: rotate(10deg);
    transform: rotate(10deg);
    background-color: #000;
    width: 110% !important;
    transform-origin: top left;
    transition: 0.5s transform, 2s margin-left;
    margin-bottom: 0;
}

.menu::before {
    position: absolute;
    content: "";
    top: -592px;
    left: -100px;
    right: -100px;
    height: 600px;
    background-color: #000;
    display: block;
}

.menu::after {
    position: absolute;
    content: "";
    bottom: -10px;
    left: -100px;
    right: -100px;
    width: 110%;
    height: 4px;
    background-color: #000;
    display: block;
    transition: 1s all;
}

.menu.uk-active::after {
    width: 0;
}

.menu li {
    text-transform: uppercase;
    color: #FFF;
    margin-right: 60px;
    font-size: 24px;
    font-weight: bold;
    transition-timing-function: cubic-bezier(.54,.02,.76,.33);
    transition: 0.5s all;
}

.menu.active li {
    transition: 3s all;
}

.menu li:nth-of-type(1) {
    transition-delay: 1s;
}

.menu li:nth-of-type(2) {
    transition-delay: 0.8s;
}

.menu li:nth-of-type(3) {
    transition-delay: 0.6s;
}

.menu li:nth-of-type(4) {
    transition-delay: 0.4s;
}

.menu li:nth-of-type(5) {
    transition-delay: 0.2s;
}
</style>
