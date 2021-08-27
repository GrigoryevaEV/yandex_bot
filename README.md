// ==UserScript==
// @name         Yandex_Bot
// @namespace    http://tampermonkey.net/
// @version      0.1
// @description  Bot!
// @author       Nezabudka
// @match        https://yandex.ru/*
// @grant        none
// ==/UserScript==
let keywords = ["Как звучит флейта", "кларнет"];
let button = document.getElementsByClassName("button")[0];

let links = document.links;
let keyword =keywords[getRandom(0,keywords.length)];
document.getElementsByName("text")[0].value= keyword;

if (button !== undefined) {
button.click();
}else{
for (let i=0; i<links.length; i++) {
if (links[i].href.includes('xn----7sbab5aqcbiddtdj1e1g.xn--p1ai')){
let link = links[i];
link.click();
console.log("Нашел строку" + links[i]);
break;
    }
   }
}
function getRandom(min,max){
return Math.floor(Math.random()*(max-min)+min);
}
