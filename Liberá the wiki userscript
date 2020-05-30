// ==UserScript==
// @name        Liberá my Wiki
// @namespace   Violentmonkey Scripts
// @match       *://banjokazooie.fandom.com/*
// @match       *://half-life.fandom.com/*
// @grant       none
// @version     1.0
// @author      LongJohn-Silver
// @description Converts Fandom Wiki links to MediaWiki links
// ==/UserScript==

function test(url){
    return !!url.match(/^(|http(s?):\/\/)(|www.)banjokazooie.fandom.com(\/.*|$)/gim);
}

function getNewPagePlease(url){
    return 'https://banjokazooiewiki.com/';
}

function fixWikiStuff(){
    var links = Array.prototype.slice.call(document.links, 0);
    links.filter(function(link){
        if(test(link.href)){
            var greatNewLink = getNewPagePlease(link.href);
            if(link.hasAttribute('data-outbound-url')) link.setAttribute('data-outbound-url', greatNewLink);
            link.setAttribute('href', greatNewLink);
        }
    });
}

function test(url){
    return !!url.match(/^(|http(s?):\/\/)(|www.)half-life.fandom.com(\/.*|$)/gim);
}

function getNewPagePlease(url){
    return 'https://combineoverwiki.net/';
}

function fixWikiStuff(){
    var links = Array.prototype.slice.call(document.links, 0);
    links.filter(function(link){
        if(test(link.href)){
            var greatNewLink = getNewPagePlease(link.href);
            if(link.hasAttribute('data-outbound-url')) link.setAttribute('data-outbound-url', greatNewLink);
            link.setAttribute('href', greatNewLink);
        }
    });
}

if(test(window.location.href)){window.location.assign(getNewPagePlease(window.location.href));}

window.onload = fixWikiStuff;
setInterval(fixWikiStuff, 50);
