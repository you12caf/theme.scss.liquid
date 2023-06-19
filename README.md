# theme.scss.liquid
@charset "utf-8";

/**
 * All the variables that can be used to extract Shopify global settings
 */

/* Colors */

$background      : {{settings.background}};
$light-background: {{settings.light_background}};
$heading-color   : {{settings.heading_color}};
$text-color      : {{settings.text_color}};
$text-color-light: {{settings.text_light_color}};
$link-color      : {{settings.link_color}};
$border-color    : {{settings.background | color_mix: settings.text_color, 85}};

$button-background: {{settings.button_background}};
$button-text-color: {{settings.button_text_color}};

$header-background       : {{settings.header_background}};
$header-heading-color    : {{settings.header_heading_color}};
$header-light-text-color : {{settings.header_light_color}};
$header-border-color     : {{settings.header_background | color_mix: settings.header_heading_color, 85}};

$footer-background    : {{settings.footer_background}};
$footer-text-color    : {{settings.footer_text_color}};
$footer-heading-color : {{settings.footer_heading_color}};
$footer-border-color  : {{settings.footer_background | color_mix: settings.footer_text_color, 85}};

$navigation-background      : {{settings.navigation_background}};
$navigation-text-color      : {{settings.navigation_text_color}};
$navigation-text-color-light: rgba($navigation-text-color, 0.5);
$navigation-border-color    : rgba($navigation-text-color, 0.25);

$newsletter-popup-background : {{settings.newsletter_popup_background}};
$newsletter-popup-text-color : {{settings.newsletter_popup_text_color}};

$secondary-elements-background       : {{settings.secondary_elements_background}};
$secondary-elements-text-color       : {{settings.secondary_elements_text_color}};
$secondary-elements-text-color-light : rgba($secondary-elements-text-color, 0.5);
$secondary-elements-border-color     : rgba($secondary-elements-text-color, 0.25);

$product-sale-price-color: {{settings.product_on_sale_color}};

/* Typography */

{{ settings.heading_font | font_face }}
{{ settings.text_font | font_face }}

{%- assign text_font_bold = settings.text_font | font_modify: 'weight', 'bolder' -%}
{%- assign text_font_italic = settings.text_font | font_modify: 'style', 'italic' -%}
{%- assign text_font_bold_italic = text_font_bold | font_modify: 'style', 'italic' -%}

{{ text_font_bold | font_face }}
{{ text_font_italic | font_face }}
{{ text_font_bold_italic | font_face }}

$heading-font-family : {{settings.heading_font.family}}, {{ settings.heading_font.fallback_families }};
$heading-font-weight : {{settings.heading_font.weight}};
$heading-font-style  : {{settings.heading_font.style}};
$heading-font-size   : {{settings.heading_size}};

$text-font-family : {{settings.text_font.family}}, {{ settings.text_font.fallback_families }};
$text-font-weight : {{settings.text_font.weight}};
$text-font-style  : {{settings.text_font.style}};

$uppercase-heading: {% if settings.uppercase_heading %}true{% else %}false{% endif %};

$base-text-font-size   : {{settings.base_text_font_size}}px;
$default-text-font-size: 14px;

/* Products */

$product-info-alignment         : {{settings.product_info_alignment}};
$product-show-price-on-hover    : {{settings.product_show_price_on_hover}};
$product-list-horizontal-spacing: {{settings.product_list_horizontal_spacing}};
$product-list-vertical-spacing  : {{settings.product_list_vertical_spacing}};

$cursor-zoom-in-svg    : "{{ 'cursor-zoom-in.svg' | asset_url }}";
$cursor-zoom-in-2x-svg : "{{ 'cursor-zoom-in-2x.svg' | asset_url }}";

/* Animation */

$drawer-transition-timing: cubic-bezier(0.645, 0.045, 0.355, 1);
$show-page-transition: {% if settings.show_page_transition %}true{% else %}false{% endif %};
$show-image-zooming: {% if settings.show_image_zooming %}true{% else %}false{% endif %};
$show-element-staggering: {% if settings.show_element_staggering %}true{% else %}false{% endif %};

/* Other */

$header-base-height: 80px; /* We use this value for browsers that do not support CSS variables */

/**
 * ----------------------------------------------------------------------------------------------
 * This is a variation of Normalize.css (http://necolas.github.io/normalize.css/)
 * ----------------------------------------------------------------------------------------------
 */

/**
 * Base
 */

*,
*:before,
*:after {
  -webkit-box-sizing: border-box !important;
  box-sizing: border-box !important;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

html {
  font-family: sans-serif;
  -webkit-text-size-adjust: 100%;
  -moz-text-size-adjust: 100%;
  -ms-text-size-adjust: 100%;
  text-size-adjust: 100%;
  -ms-overflow-style: -ms-autohiding-scrollbar;
}

body {
  margin: 0;
}

[hidden] {
  display: none;
}

/**
 * HTML5 display definitions
 */

article,
aside,
details,
figcaption,
figure,
footer,
header,
main,
nav,
section,
summary {
  display: block;
}

audio,
canvas,
progress,
video {
  display: inline-block;
  vertical-align: baseline;
}

audio:not([controls]) {
  display: none;
  height: 0;
}

/**
 * Text-level semantic
 */

:active {
  outline: none;
}

a {
  color: inherit;
  background-color: transparent;
  text-decoration: none;

  &:active,
  &:hover {
    outline: 0;
  }
}

b,
strong {
  font-weight: bold;
}

small {
  font-size: 80%;
}

p,
h1,
h2,
h3,
h4,
h5,
h6 {
  margin-top: 0;
  font-size: inherit;
  font-weight: inherit;
}

p:last-child,
h1:last-child,
h2:last-child,
h3:last-child,
h4:last-child,
h5:last-child,
h6:last-child {
  margin-bottom: 0;
}

/**
 * Embedded content
 */

img {
  max-width: 100%;
  height: auto;
  border-style: none;
  vertical-align: top;
}

svg:not(:root) {
  overflow: hidden;
}

/**
 * Grouping content
 */

ul,
ol {
  margin: 0;
  padding: 0;
  list-style-position: inside;
}

pre {
  overflow: auto;
}

code,
kbd,
pre,
samp {
  font-family: monospace, monospace;
  font-size: 16px;
}

/**
 * Forms
 */

button,
input,
optgroup,
select,
textarea {
  color: inherit;
  font: inherit;
  margin: 0;
}

button,
input[type="submit"] {
  padding: 0;
  overflow: visible;
  background: none;
  border: none;
  border-radius: 0;
  -webkit-appearance: none;
}

button,
select {
  text-transform: none;
}

button,
html input[type="button"],
input[type="reset"],
input[type="submit"] {
  -webkit-appearance: button;
  cursor: pointer;
}

button[disabled],
html input[disabled] {
  cursor: default;
}

button::-moz-focus-inner,
input::-moz-focus-inner {
  border: 0;
  padding: 0;
}

input {
  line-height: normal;
  -webkit-appearance: none;
  border-radius: 0;
}

input[type="checkbox"],
input[type="radio"] {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  padding: 0;
}

input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  height: auto;
}

input[type="search"] {
  -webkit-appearance: none;
  -webkit-box-sizing: content-box;
  box-sizing: content-box;
}

input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}

input::-webkit-input-placeholder,
textarea::-webkit-input-placeholder {
  color: inherit;
}

input:-ms-input-placeholder,
textarea:-ms-input-placeholder {
  color: inherit;
}

input::placeholder,
textarea::placeholder {
  color: inherit;
}

fieldset {
  border: 1px solid #c0c0c0;
  margin: 0 2px;
  padding: 6px 10px 12px;
}

legend {
  border: 0;
  padding: 0;
}

textarea {
  overflow: auto;
}

optgroup {
  font-weight: bold;
}

/**
 * Tables
 */

table {
  border-collapse: collapse;
  border-spacing: 0;
}

td,
th {
  padding: 0;
}
/*! Avalanche | MIT License | @colourgarden */

$phone:            "screen and (max-width: 640px)";
$tablet:           "screen and (min-width: 641px) and (max-width: 1007px)";
$tablet-and-up:    "screen and (min-width: 641px)";
$pocket:           "screen and (max-width: 1007px)";
$lap:              "screen and (min-width: 1008px) and (max-width: 1239px)";
$lap-and-up:       "screen and (min-width: 1008px)";
$desk:             "screen and (min-width: 1240px)";
$widescreen:       "screen and (min-width: 1500px)";

@mixin av-mq($alias) {
  @if $alias == "phone" {
    @media #{$phone} {
      @content;
    }
  } @else if $alias == "tablet" {
    @media #{$tablet} {
      @content;
    }
  } @else if $alias == "tablet-and-up" {
    @media #{$tablet-and-up} {
      @content;
    }
  } @else if $alias == "pocket" {
    @media #{$pocket} {
      @content;
    }
  } @else if $alias == "lap" {
    @media #{$lap} {
      @content;
    }
  } @else if $alias == "lap-and-up" {
    @media #{$lap-and-up} {
      @content;
    }
  } @else if $alias == "desk" {
    @media #{$desk} {
      @content;
    }
  } @else if $alias == "widescreen" {
    @media #{$widescreen} {
      @content;
    }
  }
}

/*------------------------------------
 *   Grid LAYOUT
 *------------------------------------*/

.Grid {
  display: block;
  list-style: none;
  padding: 0;
  margin: 0 0 0 -24px;
  font-size: 0;
}

.Grid__Cell {
  box-sizing: border-box;
  display: inline-block;
  width: 100%;
  padding: 0 0 0 24px;
  margin: 0;
  vertical-align: top;
  font-size: 1rem;
}

.Grid--center {
  text-align: center;
}

.Grid--center > .Grid__Cell {
  text-align: left;
}

.Grid__Cell--center {
  display: block;
  margin: 0 auto;
}

.Grid--right {
  text-align: right;
}

.Grid--right > .Grid__Cell {
  text-align: left;
}

.Grid--middle > .Grid__Cell {
  vertical-align: middle;
}

.Grid--bottom > .Grid__Cell {
  vertical-align: bottom;
}

.Grid--m {
  margin-left: -30px;
}

.Grid--m > .Grid__Cell {
  padding-left: 30px;
}

.Grid--l {
  margin-left: -50px;
}

.Grid--l > .Grid__Cell {
  padding-left: 50px;
}

@include av-mq('desk') {
  .Grid--m {
    margin-left: -60px;
  }

  .Grid--m > .Grid__Cell {
    padding-left: 60px;
  }

  .Grid--l {
    margin-left: -80px;
  }

  .Grid--l > .Grid__Cell {
    padding-left: 80px;
  }
}

/*------------------------------------*\
    Grid WIDTHS
\*------------------------------------*/

.\31\/2, .\32\/4, .\36\/12 {
  width: 50%;
}

.\31\/3, .\34\/12 {
  width: 33.33333%;
}

.\32\/3, .\38\/12 {
  width: 66.66667%;
}

.\31\/4, .\33\/12 {
  width: 25%;
}

.\33\/4, .\39\/12 {
  width: 75%;
}

.\31\/12 {
  width: 8.33333%;
}

.\32\/12 {
  width: 16.66667%;
}

.\35\/12 {
  width: 41.66667%;
}

.\37\/12 {
  width: 58.33333%;
}

.\31\30\/12 {
  width: 83.33333%;
}

.\31\31\/12 {
  width: 91.66667%;
}

@media #{$phone} {
  .hidden-phone {
    display: none !important;
  }

  .\31\/2--phone, .\32\/4--phone, .\36\/12--phone {
    width: 50%;
  }

  .\31\/3--phone, .\34\/12--phone {
    width: 33.33333%;
  }

  .\32\/3--phone, .\38\/12--phone {
    width: 66.66667%;
  }

  .\31\/4--phone, .\33\/12--phone {
    width: 25%;
  }

  .\33\/4--phone, .\39\/12--phone {
    width: 75%;
  }

  .\31\/12--phone {
    width: 8.33333%;
  }

  .\32\/12--phone {
    width: 16.66667%;
  }

  .\35\/12--phone {
    width: 41.66667%;
  }

  .\37\/12--phone {
    width: 58.33333%;
  }

  .\31\30\/12--phone {
    width: 83.33333%;
  }

  .\31\31\/12--phone {
    width: 91.66667%;
  }
}

@media #{$tablet} {
  .hidden-tablet {
    display: none !important;
  }

  .\31\/2--tablet, .\32\/4--tablet, .\36\/12--tablet {
    width: 50%;
  }

  .\31\/3--tablet, .\34\/12--tablet {
    width: 33.33333%;
  }

  .\32\/3--tablet, .\38\/12--tablet {
    width: 66.66667%;
  }

  .\31\/4--tablet, .\33\/12--tablet {
    width: 25%;
  }

  .\33\/4--tablet, .\39\/12--tablet {
    width: 75%;
  }

  .\31\/12--tablet {
    width: 8.33333%;
  }

  .\32\/12--tablet {
    width: 16.66667%;
  }

  .\35\/12--tablet {
    width: 41.66667%;
  }

  .\37\/12--tablet {
    width: 58.33333%;
  }

  .\31\30\/12--tablet {
    width: 83.33333%;
  }

  .\31\31\/12--tablet {
    width: 91.66667%;
  }
}

@media #{$tablet-and-up} {
  .hidden-tablet-and-up {
    display: none !important;
  }

  .\31\/2--tablet-and-up, .\32\/4--tablet-and-up, .\36\/12--tablet-and-up {
    width: 50%;
  }

  .\31\/3--tablet-and-up, .\34\/12--tablet-and-up {
    width: 33.33333%;
  }

  .\32\/3--tablet-and-up, .\38\/12--tablet-and-up {
    width: 66.66667%;
  }

  .\31\/4--tablet-and-up, .\33\/12--tablet-and-up {
    width: 25%;
  }

  .\33\/4--tablet-and-up, .\39\/12--tablet-and-up {
    width: 75%;
  }

  .\31\/12--tablet-and-up {
    width: 8.33333%;
  }

  .\32\/12--tablet-and-up {
    width: 16.66667%;
  }

  .\35\/12--tablet-and-up {
    width: 41.66667%;
  }

  .\37\/12--tablet-and-up {
    width: 58.33333%;
  }

  .\31\30\/12--tablet-and-up {
    width: 83.33333%;
  }

  .\31\31\/12--tablet-and-up {
    width: 91.66667%;
  }
}

@media #{$pocket} {
  .hidden-pocket {
    display: none !important;
  }

  .\31\/2--pocket, .\32\/4--pocket, .\36\/12--pocket {
    width: 50%;
  }

  .\31\/3--pocket, .\34\/12--pocket {
    width: 33.33333%;
  }

  .\32\/3--pocket, .\38\/12--pocket {
    width: 66.66667%;
  }

  .\31\/4--pocket, .\33\/12--pocket {
    width: 25%;
  }

  .\33\/4--pocket, .\39\/12--pocket {
    width: 75%;
  }

  .\31\/12--pocket {
    width: 8.33333%;
  }

  .\32\/12--pocket {
    width: 16.66667%;
  }

  .\35\/12--pocket {
    width: 41.66667%;
  }

  .\37\/12--pocket {
    width: 58.33333%;
  }

  .\31\30\/12--pocket {
    width: 83.33333%;
  }

  .\31\31\/12--pocket {
    width: 91.66667%;
  }
}

@media #{$lap} {
  .hidden-lap {
    display: none !important;
  }

  .\31\/2--lap, .\32\/4--lap, .\36\/12--lap {
    width: 50%;
  }

  .\31\/3--lap, .\34\/12--lap {
    width: 33.33333%;
  }

  .\32\/3--lap, .\38\/12--lap {
    width: 66.66667%;
  }

  .\31\/4--lap, .\33\/12--lap {
    width: 25%;
  }

  .\33\/4--lap, .\39\/12--lap {
    width: 75%;
  }

  .\31\/12--lap {
    width: 8.33333%;
  }

  .\32\/12--lap {
    width: 16.66667%;
  }

  .\35\/12--lap {
    width: 41.66667%;
  }

  .\37\/12--lap {
    width: 58.33333%;
  }

  .\31\30\/12--lap {
    width: 83.33333%;
  }

  .\31\31\/12--lap {
    width: 91.66667%;
  }
}

@media #{$lap-and-up} {
  .hidden-lap-and-up {
    display: none !important;
  }

  .\31\/2--lap-and-up, .\32\/4--lap-and-up, .\36\/12--lap-and-up {
    width: 50%;
  }

  .\31\/3--lap-and-up, .\34\/12--lap-and-up {
    width: 33.33333%;
  }

  .\32\/3--lap-and-up, .\38\/12--lap-and-up {
    width: 66.66667%;
  }

  .\31\/4--lap-and-up, .\33\/12--lap-and-up {
    width: 25%;
  }

  .\33\/4--lap-and-up, .\39\/12--lap-and-up {
    width: 75%;
  }

  .\31\/12--lap-and-up {
    width: 8.33333%;
  }

  .\32\/12--lap-and-up {
    width: 16.66667%;
  }

  .\35\/12--lap-and-up {
    width: 41.66667%;
  }

  .\37\/12--lap-and-up {
    width: 58.33333%;
  }

  .\31\30\/12--lap-and-up {
    width: 83.33333%;
  }

  .\31\31\/12--lap-and-up {
    width: 91.66667%;
  }
}

@media #{$desk} {
  .hidden-desk {
    display: none !important;
  }

  .\31\/2--desk, .\32\/4--desk, .\36\/12--desk {
    width: 50%;
  }

  .\31\/3--desk, .\34\/12--desk {
    width: 33.33333%;
  }

  .\32\/3--desk, .\38\/12--desk {
    width: 66.66667%;
  }

  .\31\/4--desk, .\33\/12--desk {
    width: 25%;
  }

  .\33\/4--desk, .\39\/12--desk {
    width: 75%;
  }

  .\31\/12--desk {
    width: 8.33333%;
  }

  .\32\/12--desk {
    width: 16.66667%;
  }

  .\35\/12--desk {
    width: 41.66667%;
  }

  .\37\/12--desk {
    width: 58.33333%;
  }

  .\31\30\/12--desk {
    width: 83.33333%;
  }

  .\31\31\/12--desk {
    width: 91.66667%;
  }
}
/* Create each media query */
@media #{$widescreen} {
  .hidden-widescreen {
    display: none !important;
  }

  .\31\/2--widescreen, .\32\/4--widescreen, .\36\/12--widescreen {
    width: 50%;
  }

  .\31\/3--widescreen, .\34\/12--widescreen {
    width: 33.33333%;
  }

  .\32\/3--widescreen, .\38\/12--widescreen {
    width: 66.66667%;
  }

  .\31\/4--widescreen, .\33\/12--widescreen {
    width: 25%;
  }

  .\33\/4--widescreen, .\39\/12--widescreen {
    width: 75%;
  }

  .\31\/12--widescreen {
    width: 8.33333%;
  }

  .\32\/12--widescreen {
    width: 16.66667%;
  }

  .\35\/12--widescreen {
    width: 41.66667%;
  }

  .\37\/12--widescreen {
    width: 58.33333%;
  }

  .\31\30\/12--widescreen {
    width: 83.33333%;
  }

  .\31\31\/12--widescreen {
    width: 91.66667%;
  }
}
/*! PhotoSwipe main CSS by Dmitry Semenov | photoswipe.com | MIT license */
/*
	Styles for basic PhotoSwipe functionality (sliding area, open/close transitions)
*/

.pswp {
  display: none;
  position: absolute;
  width: 100%;
  height: 100%;
  left: 0;
  top: 0;
  overflow: hidden;
  -ms-touch-action: none;
  touch-action: none;
  z-index: 1500;
  -webkit-text-size-adjust: 100%;
  -webkit-backface-visibility: hidden;
  outline: none;
}

.pswp img {
  max-width: none;
}

.pswp--animate_opacity {
  opacity: 0.001; /* 0.001, because opacity:0 doesn't trigger Paint action, which causes lag at start of transition */
  will-change: opacity;
  -webkit-transition: opacity 0.5s cubic-bezier(0.4, 0, 0.22, 1);
  transition: opacity 0.5s cubic-bezier(0.4, 0, 0.22, 1);
}

.pswp--open {
  display: block;
}

.pswp--zoom-allowed .pswp__img {
  cursor: url($cursor-zoom-in-svg) 18 18, -webkit-zoom-in;
  cursor: url($cursor-zoom-in-svg) 18 18, zoom-in;
  cursor: -webkit-image-set(url($cursor-zoom-in-svg) 1x, url($cursor-zoom-in-2x-svg) 2x) 18 18, -webkit-zoom-in;
  cursor: -webkit-image-set(url($cursor-zoom-in-svg) 1x, url($cursor-zoom-in-2x-svg) 2x) 18 18, zoom-in;
}

.pswp--zoomed-in .pswp__img {
  cursor: -webkit-grab;
  cursor: grab;
}

.pswp--dragging .pswp__img {
  cursor: -webkit-grabbing;
  cursor: grabbing;
}

.pswp__bg {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background: $background;
  opacity: 0;
  -webkit-transform: translateZ(0);
  transform: translateZ(0);
  -webkit-backface-visibility: hidden;
  will-change: opacity;
}

.pswp__scroll-wrap {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.pswp__container,
.pswp__zoom-wrap {
  -ms-touch-action: none;
  touch-action: none;
  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
}

/* Prevent selection and tap highlights */
.pswp__container,
.pswp__img {
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  -webkit-tap-highlight-color: transparent;
  -webkit-touch-callout: none;
}

.pswp__container {
  -webkit-transition: -webkit-transform 0.7s cubic-bezier(0.645, 0.045, 0.355, 1);
  transition: -webkit-transform 0.7s cubic-bezier(0.645, 0.045, 0.355, 1);
  transition: transform 0.7s cubic-bezier(0.645, 0.045, 0.355, 1);
  transition: transform 0.7s cubic-bezier(0.645, 0.045, 0.355, 1), -webkit-transform 0.7s cubic-bezier(0.645, 0.045, 0.355, 1);
}

.pswp__zoom-wrap {
  position: absolute;
  width: 100%;
  -webkit-transform-origin: left top;
  transform-origin: left top;
  -webkit-transition: -webkit-transform 0.5s cubic-bezier(0.4, 0, 0.22, 1);
  transition: -webkit-transform 0.5s cubic-bezier(0.4, 0, 0.22, 1);
  transition: transform 0.5s cubic-bezier(0.4, 0, 0.22, 1);
  transition: transform 0.5s cubic-bezier(0.4, 0, 0.22, 1), -webkit-transform 0.5s cubic-bezier(0.4, 0, 0.22, 1);
}

.pswp__bg {
  will-change: opacity;
  -webkit-transition: opacity 0.5s cubic-bezier(0.4, 0, 0.22, 1);
  transition: opacity 0.5s cubic-bezier(0.4, 0, 0.22, 1);
}

.pswp--animated-in .pswp__bg,
.pswp--animated-in .pswp__zoom-wrap {
  -webkit-transition: none;
  transition: none;
}

.pswp__container,
.pswp__zoom-wrap {
  -webkit-backface-visibility: hidden;
}

.pswp__item {
  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  overflow: hidden;
}

.pswp__img {
  position: absolute;
  width: auto;
  height: auto;
  top: 0;
  left: 0;
}

.pswp__img--placeholder {
  -webkit-backface-visibility: hidden;
}

.pswp__img--placeholder--blank {
  background: $background;
}

.pswp--ie .pswp__img {
  width: 100% !important;
  height: auto !important;
  left: 0;
  top: 0;
}

/**
 * Custom UI
 */

.pswp__ui {
  position: absolute;
  visibility: hidden;
  width: 100%;
  bottom: 50px;
  opacity: 0;
  -webkit-transform: translateY(35px);
  transform: translateY(35px);
  left: 0;
  text-align: center;
  -webkit-transition: all 0.15s ease-in-out;
  transition: all 0.15s ease-in-out;
}

.pswp__button[disabled] {
  opacity: 0;
  pointer-events: none;
}

.pswp--animated-in .pswp__ui {
  visibility: visible;
  opacity: 1;
  -webkit-transform: translateY(0);
  transform: translateY(0);
}

.pswp--animated-in .pswp__ui--hidden {
  visibility: hidden;
  opacity: 0;
}

.pswp__button--close {
  margin: 0 18px;
}

.pswp__button svg {
  pointer-events: none;
}

.pswp__error-msg {
  position: absolute;
  top: 40%;
  margin: 0 15px;
  padding: 8px 15px;
  background: #e6554d;
  color: #ffffff;
  text-align: center;
}

/**
 * In our theme, we express all font sizes in PX. The reason is that our designer is very picky and want each font size to be exactly as on designed files
 * (which is good :p), but as a consequence, sometimes some font sizes scales across devices (smaller on mobile, bigger on desktop), but sometimes it's the
 * same, which make it super hard to use relative units like REM.
 */
@function to-size($size) {
  @return $base-text-font-size - ($default-text-font-size - $size);
}

/*
 * Precomputed linear color channel values, for use in contrast calculations.
 * See https://www.w3.org/TR/WCAG20-TECHS/G17.html#G17-tests
 *
 * Algorithm, for c in 0 to 255:
 * f(c) {
 *   c = c / 255;
 *   return c < 0.03928 ? c / 12.92 : Math.pow((c + 0.055) / 1.055, 2.4);
 * }
 *
 * This lookup table is needed since there is no `pow` in SASS.
 */

$linear-channel-values:
  0
  .0003035269835488375
  .000607053967097675
  .0009105809506465125
  .00121410793419535
  .0015176349177441874
  .001821161901293025
  .0021246888848418626
  .0024282158683907
  .0027317428519395373
  .003035269835488375
  .003346535763899161
  .003676507324047436
  .004024717018496307
  .004391442037410293
  .004776953480693729
  .005181516702338386
  .005605391624202723
  .006048833022857054
  .006512090792594475
  .006995410187265387
  .007499032043226175
  .008023192985384994
  .008568125618069307
  .009134058702220787
  .00972121732023785
  .010329823029626936
  .010960094006488246
  .011612245179743885
  .012286488356915872
  .012983032342173012
  .013702083047289686
  .014443843596092545
  .01520851442291271
  .01599629336550963
  .016807375752887384
  .017641954488384078
  .018500220128379697
  .019382360956935723
  .0202885630566524
  .021219010376003555
  .022173884793387385
  .02315336617811041
  .024157632448504756
  .02518685962736163
  .026241221894849898
  .027320891639074894
  .028426039504420793
  .0295568344378088
  .030713443732993635
  .03189603307301153
  .033104766570885055
  .03433980680868217
  .03560131487502034
  .03688945040110004
  .0382043715953465
  .03954623527673284
  .04091519690685319
  .042311410620809675
  .043735029256973465
  .04518620438567554
  .046665086336880095
  .04817182422688942
  .04970656598412723
  .05126945837404324
  .052860647023180246
  .05448027644244237
  .05612849004960009
  .05780543019106723
  .0595112381629812
  .06124605423161761
  .06301001765316767
  .06480326669290577
  .06662593864377289
  .06847816984440017
  .07036009569659588
  .07227185068231748
  .07421356838014963
  .07618538148130785
  .07818742180518633
  .08021982031446832
  .0822827071298148
  .08437621154414882
  .08650046203654976
  .08865558628577294
  .09084171118340768
  .09305896284668745
  .0953074666309647
  .09758734714186246
  .09989872824711389
  .10224173308810132
  .10461648409110419
  .10702310297826761
  .10946171077829933
  .1119324278369056
  .11443537382697373
  .11697066775851084
  .11953842798834562
  .12213877222960187
  .12477181756095049
  .12743768043564743
  .1301364766903643
  .13286832155381798
  .13563332965520566
  .13843161503245183
  .14126329114027164
  .14412847085805777
  .14702726649759498
  .14995978981060856
  .15292615199615017
  .1559264637078274
  .1589608350608804
  .162029375639111
  .1651321945016676
  .16826940018969075
  .1714411007328226
  .17464740365558504
  .17788841598362912
  .18116424424986022
  .184474994500441
  .18782077230067787
  .19120168274079138
  .1946178304415758
  .19806931955994886
  .20155625379439707
  .20507873639031693
  .20863687014525575
  .21223075741405523
  .21586050011389926
  .2195261997292692
  .2232279573168085
  .22696587351009836
  .23074004852434915
  .23455058216100522
  .238397573812271
  .24228112246555486
  .24620132670783548
  .25015828472995344
  .25415209433082675
  .2581828529215958
  .26225065752969623
  .26635560480286247
  .2704977910130658
  .27467731206038465
  .2788942634768104
  .2831487404299921
  .2874408377269175
  .29177064981753587
  .2961382707983211
  .3005437944157765
  .3049873140698863
  .30946892281750854
  .31398871337571754
  .31854677812509186
  .32314320911295075
  .3277780980565422
  .33245153634617935
  .33716361504833037
  .3419144249086609
  .3467040563550296
  .35153259950043936
  .3564001441459435
  .3613067797835095
  .3662525955988395
  .3712376804741491
  .3762621229909065
  .38132601143253014
  .386429433787049
  .39157247774972326
  .39675523072562685
  .4019777798321958
  .4072402119017367
  .41254261348390375
  .4178850708481375
  .4232676699860717
  .4286904966139066
  .43415363617474895
  .4396571738409188
  .44520119451622786
  .45078578283822346
  .45641102318040466
  .4620769996544071
  .467783796112159
  .47353149614800955
  .4793201831008268
  .4851499400560704
  .4910208498478356
  .4969329950608704
  .5028864580325687
  .5088813208549338
  .5149176653765214
  .5209955732043543
  .5271151257058131
  .5332764040105052
  .5394794890121072
  .5457244613701866
  .5520114015120001
  .5583403896342679
  .5647115057049292
  .5711248294648731
  .5775804404296506
  .5840784178911641
  .5906188409193369
  .5972017883637634
  .6038273388553378
  .6104955708078648
  .6172065624196511
  .6239603916750761
  .6307571363461468
  .6375968739940326
  .6444796819705821
  .6514056374198242
  .6583748172794485
  .665387298282272
  .6724431569576875
  .6795424696330938
  .6866853124353135
  .6938717612919899
  .7011018919329731
  .7083757798916868
  .7156935005064807
  .7230551289219693
  .7304607400903537
  .7379104087727308
  .7454042095403874
  .7529422167760779
  .7605245046752924
  .768151147247507
  .7758222183174236
  .7835377915261935
  .7912979403326302
  .799102738014409
  .8069522576692516
  .8148465722161012
  .8227857543962835
  .8307698767746546
  .83879901174074
  .846873231509858
  .8549926081242338
  .8631572134541023
  .8713671191987972
  .8796223968878317
  .8879231178819663
  .8962693533742664
  .9046611743911496
  .9130986517934192
  .9215818562772946
  .9301108583754237
  .938685728457888
  .9473065367331999
  .9559733532492861
  .9646862478944651
  .9734452903984125
  .9822505503331171
  .9911020971138298
  1;

/**
 * Calculate the luminance for a color.
 * See https://www.w3.org/TR/WCAG20-TECHS/G17.html#G17-tests
 */
@function luminance($color) {
  $red: nth($linear-channel-values, red($color) + 1);
  $green: nth($linear-channel-values, green($color) + 1);
  $blue: nth($linear-channel-values, blue($color) + 1);

  @return .2126 * $red + .7152 * $green + .0722 * $blue;
}

/**
 * Calculate the contrast ratio between two colors.
 * See https://www.w3.org/TR/WCAG20-TECHS/G17.html#G17-tests
 */
@function contrast($back, $front) {
  $back-lum: luminance($back) + .05;
  $fore-lum: luminance($front) + .05;

  @return max($back-lum, $fore-lum) / min($back-lum, $fore-lum);
}
.js .no-js,
.no-js .hide-no-js {
  display: none !important;
}

.no-scroll {
  overflow: hidden;
}

body:not(.is-tabbing) button:focus,
body:not(.is-tabbing) input:focus,
body:not(.is-tabbing) select:focus,
body:not(.is-tabbing) textarea:focus {
  outline: none;
}

[data-scrollable] {
  overflow: auto;
  /*-webkit-overflow-scrolling: touch;*/
}

.Container {
  margin: 0 auto;
  padding: 0 24px;
}

.Container--narrow {
  max-width: 1420px;
}

.Container--extraNarrow {
  max-width: 800px;
}

/*
   This fixes an issue in IE10/11 when using min-height in flex children
   @info: https://github.com/philipwalton/flexbugs#3-min-height-on-a-flex-container-wont-apply-to-its-flex-items
*/

.FlexboxIeFix {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: horizontal;
  -webkit-box-direction: normal;
  -ms-flex-direction: row;
  flex-direction: row;
}

@include av-mq('tablet-and-up') {
  .Container {
    padding: 0 50px;
  }
}

@include av-mq('desk') {
  .Container {
    padding: 0 80px;
  }
}
/**
 * Very general typographic rules that are applied site wide
 */

html {
  font-size: $base-text-font-size;
}

body {
  font-family: $text-font-family;
  font-weight: $text-font-weight;
  font-style: $text-font-style;
  color: $text-color;
  background: $background;
  line-height: 1.65;
}

.Link {
  -webkit-transition: color 0.2s ease-in-out, opacity 0.2s ease-in-out;
  transition: color 0.2s ease-in-out, opacity 0.2s ease-in-out;
}

.supports-hover .Link--primary:hover,
.Link--primary.is-active {
  color: $text-color;
}

.supports-hover .Link--secondary:hover,
.Link--secondary.is-active {
  color: $text-color-light;
}

.Link--underline {
  position: relative;
  display: inline-block;

  &::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 1px;
    left: 0;
    bottom: -1px;
    background: currentColor;
    -webkit-transform: scale(1, 1);
    transform: scale(1, 1);
    -webkit-transform-origin: left center;
    transform-origin: left center;
    -webkit-transition: -webkit-transform 0.2s ease-in-out;
    transition: -webkit-transform 0.2s ease-in-out;
    transition: transform 0.2s ease-in-out;
    transition: transform 0.2s ease-in-out, -webkit-transform 0.2s ease-in-out;
  }

  @media (-moz-touch-enabled: 0), (hover: hover) {
    &:hover::before {
      -webkit-transform: scale(0, 1);
      transform: scale(0, 1);
    }
  }
}

.Link--underlineShort::before {
  @if $uppercase-heading {
    width: calc(100% - 0.2em);
  } @else {
    width: 100%;
  }
}

.Link--underlineNative {
  text-decoration: underline;
  text-underline-position: under;
}

.Heading {
  font-family: $heading-font-family;
  font-weight: $heading-font-weight;
  font-style: $heading-font-style;
  color: $heading-color;
  -webkit-transition: color 0.2s ease-in-out;
  transition: color 0.2s ease-in-out;

  @if $uppercase-heading {
    letter-spacing: 0.2em;
    text-transform: uppercase;
  }
}

.Text--subdued {
  color: $text-color-light;
}

.Text--alignCenter {
  text-align: center !important;
}

.Text--alignRight {
  text-align: right !important;
}

.Icon-Wrapper--clickable {
  position: relative;
  background: transparent;

  /* This is used to increase the clickable area */
  &::before {
    position: absolute;
    content: '';
    top: -8px;
    right: -12px;
    left: -12px;
    bottom: -8px;
    -webkit-transform: translateZ(0);
    transform: translateZ(0); /* Needed to avoid a glitch on iOS */
  }
}

.Icon {
  display: inline-block;
  height: 1em;
  width: 1em;
  fill: currentColor;
  vertical-align: middle;
  stroke-width: 1px;
  background: none;
  pointer-events: none;
}

.u-visually-hidden {
  position: absolute !important;
  overflow: hidden;
  clip: rect(0 0 0 0);
  height: 1px;
  width: 1px;
  margin: -1px;
  padding: 0;
  border: 0;
}

@if $heading-font-size == 'small' {
  .u-h1 {
    font-size: 20px;
  }

  .u-h2 {
    font-size: 18px;
  }

  .u-h3 {
    font-size: 16px;
  }

  .u-h4 {
    font-size: 15px;
  }

  .u-h5 {
    font-size: 13px;
  }

  .u-h6 {
    font-size: 12px;
  }

  .u-h7 {
    font-size: 11px;
  }

  .u-h8 {
    font-size: 10px;
  }
} @else if $heading-font-size == 'normal' {
  .u-h1 {
    font-size: 22px;
  }

  .u-h2 {
    font-size: 20px;
  }

  .u-h3 {
    font-size: 18px;
  }

  .u-h4 {
    font-size: 16px;
  }

  .u-h5 {
    font-size: 14px;
  }

  .u-h6 {
    font-size: 13px;
  }

  .u-h7 {
    font-size: 12px;
  }

  .u-h8 {
    font-size: 12px;
  }
} @else {
  .u-h1 {
    font-size: 24px;
  }

  .u-h2 {
    font-size: 22px;
  }

  .u-h3 {
    font-size: 20px;
  }

  .u-h4 {
    font-size: 18px;
  }

  .u-h5 {
    font-size: 16px;
  }

  .u-h6 {
    font-size: 15px;
  }

  .u-h7 {
    font-size: 13px;
  }

  .u-h8 {
    font-size: 13px;
  }
}

@include av-mq('tablet-and-up') {
  @if $heading-font-size == 'small' {
    .u-h1 {
      font-size: 20px;
    }

    .u-h2 {
      font-size: 18px;
    }

    .u-h3 {
      font-size: 18px;
    }

    .u-h4 {
      font-size: 16px;
    }

    .u-h5 {
      font-size: 13px;
    }

    .u-h6 {
      font-size: 12px;
    }

    .u-h7 {
      font-size: 11px;
    }

    .u-h8 {
      font-size: 10px;
    }
  } @else if $heading-font-size == 'normal' {
    .u-h1 {
      font-size: 22px;
    }

    .u-h2 {
      font-size: 20px;
    }

    .u-h3 {
      font-size: 20px;
    }

    .u-h4 {
      font-size: 17px;
    }

    .u-h5 {
      font-size: 14px;
    }

    .u-h6 {
      font-size: 13px;
    }

    .u-h7 {
      font-size: 12px;
    }

    .u-h8 {
      font-size: 12px;
    }
  } @else {
    .u-h1 {
      font-size: 24px;
    }

    .u-h2 {
      font-size: 22px;
    }

    .u-h3 {
      font-size: 20px;
    }

    .u-h4 {
      font-size: 19px;
    }

    .u-h5 {
      font-size: 16px;
    }

    .u-h6 {
      font-size: 15px;
    }

    .u-h7 {
      font-size: 13px;
    }

    .u-h8 {
      font-size: 13px;
    }
  }
}

@if $show-page-transition {
  .js .PageTransition {
    position: fixed;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    background: $background;
    z-index: 1000;
    opacity: 1;
    visibility: visible;
    pointer-events: none;
  }
}
/**
 * ----------------------------------------------------------------------------
 * Standard button
 * ----------------------------------------------------------------------------
 */

.Button {
  position: relative;
  display: inline-block;
  padding: 14px 28px;
  line-height: normal;
  border: 1px solid transparent;
  border-radius: 0;
  text-transform: uppercase;
  font-size: to-size(12px);
  text-align: center;
  letter-spacing: 0.2em;
  font-family: $heading-font-family;
  font-weight: $heading-font-weight;
  font-style: $heading-font-style;
  background-color: transparent;
  -webkit-transition: color 0.45s cubic-bezier(0.785, 0.135, 0.15, 0.86), border 0.45s cubic-bezier(0.785, 0.135, 0.15, 0.86);
  transition: color 0.45s cubic-bezier(0.785, 0.135, 0.15, 0.86), border 0.45s cubic-bezier(0.785, 0.135, 0.15, 0.86);
  z-index: 1;
  -webkit-tap-highlight-color: initial;

  &::before {
    position: absolute;
    content: '';
    display: block;
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
    width: 100%;
    height: 100%;
    -webkit-transform: scale(1, 1);
    transform: scale(1, 1);
    -webkit-transform-origin: left center;
    transform-origin: left center;
    z-index: -1;
  }

  @media (-moz-touch-enabled: 0), (hover: hover) {
    &:not([disabled])::before {
      -webkit-transition: -webkit-transform 0.45s cubic-bezier(0.785, 0.135, 0.15, 0.86);
      transition: -webkit-transform 0.45s cubic-bezier(0.785, 0.135, 0.15, 0.86);
      transition: transform 0.45s cubic-bezier(0.785, 0.135, 0.15, 0.86);
      transition: transform 0.45s cubic-bezier(0.785, 0.135, 0.15, 0.86), -webkit-transform 0.45s cubic-bezier(0.785, 0.135, 0.15, 0.86);
    }

    &:not([disabled]):hover::before {
      -webkit-transform-origin: right center;
      transform-origin: right center;
      -webkit-transform: scale(0, 1);
      transform: scale(0, 1);
    }
  }

  &[disabled] {
    cursor: not-allowed;
  }
}

.Button--primary {
  color: $button-text-color;
  border-color: $button-background;

  &::before {
    background-color: $button-background;
  }

  @media (-moz-touch-enabled: 0), (hover: hover) {
    &:not([disabled]):hover {
      @if ((contrast($button-background, $light-background) > 2.5) or ($button-text-color == $background)) {
        color: $button-background;
      } @else {
        color: $button-text-color;
      }

      background-color: transparent;
    }
  }
}

.Button--secondary {
  color: $text-color-light;
  border: 1px solid rgba($text-color-light, 0.2);

  &::before {
    background-color: $button-background;
    -webkit-transform-origin: right center;
    transform-origin: right center;
    -webkit-transform: scale(0, 1);
    transform: scale(0, 1);
  }

  @media (-moz-touch-enabled: 0), (hover: hover) {
    &:not([disabled]):hover {
      color: $button-text-color;
      border-color: $button-background;
    }

    &:not([disabled]):hover::before {
      -webkit-transform-origin: left center;
      transform-origin: left center;
      -webkit-transform: scale(1, 1);
      transform: scale(1, 1);
    }
  }
}

.Button--full {
  width: 100%;
}

.Button--stretched {
  padding-left: 40px;
  padding-right: 40px;
}

.Button--small {
  font-size: to-size(10px);
  padding: 12px 24px;
}

.Button__SeparatorDot {
  display: inline-block;
  margin: 0 18px;
  content: '';
  height: 3px;
  width: 3px;
  border-radius: 100%;
  background: currentColor;
}

.ButtonWrapper {
  text-align: center;
}

/* We allow those buttons to have secondary state. The secondary state is displayed (for instance during loading time) when
   the class "Button--secondaryState" is added */

.Button__PrimaryState,
.Button__SecondaryState {
  display: block;
  -webkit-transition: opacity 0.4s cubic-bezier(0.75, 0, 0.125, 1), -webkit-transform 0.4s cubic-bezier(0.75, 0, 0.125, 1);
  transition: opacity 0.4s cubic-bezier(0.75, 0, 0.125, 1), -webkit-transform 0.4s cubic-bezier(0.75, 0, 0.125, 1);
  transition: transform 0.4s cubic-bezier(0.75, 0, 0.125, 1), opacity 0.4s cubic-bezier(0.75, 0, 0.125, 1);
  transition: transform 0.4s cubic-bezier(0.75, 0, 0.125, 1), opacity 0.4s cubic-bezier(0.75, 0, 0.125, 1), -webkit-transform 0.4s cubic-bezier(0.75, 0, 0.125, 1);
}

.Button__SecondaryState {
  position: absolute;
  left: 50%;
  top: 50%;
  width: 100%;
  text-align: center;
  opacity: 0;
  -webkit-transform: translate(-50%, 100%);
  transform: translate(-50%, 100%);
}

.Button--secondaryState {
  .Button__PrimaryState {
    opacity: 0;
    -webkit-transform: translateY(-100%);
    transform: translateY(-100%);
  }

  .Button__SecondaryState {
    opacity: 1;
    -webkit-transform: translate(-50%, -50%);
    transform: translate(-50%, -50%);
  }
}

/**
 * ----------------------------------------------------------------------------
 * Button group
 * ----------------------------------------------------------------------------
 */

.ButtonGroup {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -ms-flex-wrap: wrap;
  flex-wrap: wrap;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  margin: -12px;
}

.ButtonGroup__Item {
  margin: 12px;
}

.ButtonGroup__Item--expand {
  -webkit-box-flex: 1;
  -ms-flex: 1 1 0px;
  flex: 1 1 0;
}

.ButtonGroup--spacingSmall {
  margin: -8px;

  .ButtonGroup__Item {
    margin: 8px;
  }
}

.ButtonGroup--sameSize .ButtonGroup__Item {
  -webkit-box-flex: 0;
  -ms-flex: 0 1 auto;
  flex: 0 1 auto;
  white-space: nowrap;
  max-width: 245px;

  @supports ((-o-object-fit: cover) or (object-fit: cover)) {
    -webkit-box-flex: 1;
    -ms-flex: 1 1 0px;
    flex: 1 1 0; /* There is a bug in IE11 so we're forced to use this trick */
  }
}

@include av-mq('tablet-and-up') {
  @supports (display: inline-grid) {
    .ButtonGroup--sameSize {
      display: inline-grid;
      grid-template-columns: 1fr 1fr;
    }

    .ButtonGroup--sameSize .ButtonGroup__Item {
      max-width: none;
    }
  }
}

/**
 * ----------------------------------------------------------------------------
 * Round button
 *
 * Those buttons are not really button like the others, but they are used in
 * lot of different places to hold things like icons
 * ----------------------------------------------------------------------------
 */

.RoundButton {
  position: relative;
  width: 45px;
  height: 45px;
  border: none;
  border-radius: 50%;
  background: $button-text-color;
  color: $button-background;
  cursor: pointer;
  text-align: center;
  z-index: 1;
  -webkit-box-shadow: 0 2px 10px rgba(#363636, 0.15);
  box-shadow: 0 2px 10px rgba(#363636, 0.15);
  vertical-align: middle;
  line-height: 0;
  -webkit-transform: scale(1.001);
  transform: scale(1.001); /* Avoid rounding error during animation in Chrome */
  -webkit-transition: background 0.15s ease-in-out, opacity 0.15s ease-in-out, color 0.2s ease-in-out, -webkit-transform 0.2s ease-in-out;
  transition: background 0.15s ease-in-out, opacity 0.15s ease-in-out, color 0.2s ease-in-out, -webkit-transform 0.2s ease-in-out;
  transition: background 0.15s ease-in-out, opacity 0.15s ease-in-out, transform 0.2s ease-in-out, color 0.2s ease-in-out;
  transition: background 0.15s ease-in-out, opacity 0.15s ease-in-out, transform 0.2s ease-in-out, color 0.2s ease-in-out, -webkit-transform 0.2s ease-in-out;
  overflow: hidden;

  &.is-active {
    background: $button-background;
    color: $button-text-color;
    outline: none;
  }

  svg {
    height: 15px;
    width: 15px;
    fill: currentColor;
  }
}

.RoundButton--small {
  width: 35px;
  height: 35px;

  svg {
    height: 14px;
    width: 14px;
  }
}

.RoundButton--medium {
  width: 50px;
  height: 50px;

  svg {
    height: 18px;
    width: 18px;
  }
}

.RoundButton--large {
  width: 55px;
  height: 55px;

  svg {
    height: 15px;
    width: 15px;
  }
}

.RoundButton--flat {
  -webkit-box-shadow: 0 1px 5px rgba(#363636, 0.15);
  box-shadow: 0 1px 5px rgba(#363636, 0.15);
  color: rgba($button-background, 0.5);
}

/* We allow those buttons to have secondary state. The secondary state is displayed (for instance during loading time) when
   the class "RoundButton--withSecondaryState" is added */

.RoundButton__PrimaryState,
.RoundButton__SecondaryState {
  display: block;
  -webkit-transition: opacity 0.4s cubic-bezier(0.75, 0, 0.125, 1), -webkit-transform 0.4s cubic-bezier(0.75, 0, 0.125, 1);
  transition: opacity 0.4s cubic-bezier(0.75, 0, 0.125, 1), -webkit-transform 0.4s cubic-bezier(0.75, 0, 0.125, 1);
  transition: transform 0.4s cubic-bezier(0.75, 0, 0.125, 1), opacity 0.4s cubic-bezier(0.75, 0, 0.125, 1);
  transition: transform 0.4s cubic-bezier(0.75, 0, 0.125, 1), opacity 0.4s cubic-bezier(0.75, 0, 0.125, 1), -webkit-transform 0.4s cubic-bezier(0.75, 0, 0.125, 1);
}

.RoundButton__SecondaryState {
  position: absolute;
  left: 50%;
  top: 50%;
  width: 100%;
  text-align: center;
  opacity: 0;
  -webkit-transform: translate(-50%, 100%);
  transform: translate(-50%, 100%);
}

.RoundButton--secondaryState {
  .RoundButton__PrimaryState {
    opacity: 0;
    -webkit-transform: translateY(-100%);
    transform: translateY(-100%);
  }

  .RoundButton__SecondaryState {
    opacity: 1;
    -webkit-transform: translate(-50%, -50%);
    transform: translate(-50%, -50%);
  }
}

/* Animation states */

@-webkit-keyframes buttonFromLeftToRight {
  0% {
    -webkit-transform: translateX(0%);
    transform: translateX(0%);
  }

  25% {
    opacity: 0;
    -webkit-transform: translateX(100%);
    transform: translateX(100%);
  }

  50% {
    opacity: 0;
    -webkit-transform: translateX(-100%);
    transform: translateX(-100%);
  }

  75% {
    opacity: 1;
    -webkit-transform: translateX(0%);
    transform: translateX(0%);
  }
}

@keyframes buttonFromLeftToRight {
  0% {
    -webkit-transform: translateX(0%);
    transform: translateX(0%);
  }

  25% {
    opacity: 0;
    -webkit-transform: translateX(100%);
    transform: translateX(100%);
  }

  50% {
    opacity: 0;
    -webkit-transform: translateX(-100%);
    transform: translateX(-100%);
  }

  75% {
    opacity: 1;
    -webkit-transform: translateX(0%);
    transform: translateX(0%);
  }
}

@-webkit-keyframes buttonFromRightToLeft {
  0% {
    -webkit-transform: translateX(0%);
    transform: translateX(0%);
  }

  25% {
    opacity: 0;
    -webkit-transform: translateX(-100%);
    transform: translateX(-100%);
  }

  50% {
    opacity: 0;
    -webkit-transform: translateX(100%);
    transform: translateX(100%);
  }

  75% {
    opacity: 1;
    -webkit-transform: translateX(0%);
    transform: translateX(0%);
  }
}

@keyframes buttonFromRightToLeft {
  0% {
    -webkit-transform: translateX(0%);
    transform: translateX(0%);
  }

  25% {
    opacity: 0;
    -webkit-transform: translateX(-100%);
    transform: translateX(-100%);
  }

  50% {
    opacity: 0;
    -webkit-transform: translateX(100%);
    transform: translateX(100%);
  }

  75% {
    opacity: 1;
    -webkit-transform: translateX(0%);
    transform: translateX(0%);
  }
}

@-webkit-keyframes buttonFromTopToBottom {
  0% {
    -webkit-transform: translateY(0%);
    transform: translateY(0%);
  }

  25% {
    opacity: 0;
    -webkit-transform: translateY(100%);
    transform: translateY(100%);
  }

  50% {
    opacity: 0;
    -webkit-transform: translateY(-100%);
    transform: translateY(-100%);
  }

  75% {
    opacity: 1;
    -webkit-transform: translateY(0%);
    transform: translateY(0%);
  }
}

@keyframes buttonFromTopToBottom {
  0% {
    -webkit-transform: translateY(0%);
    transform: translateY(0%);
  }

  25% {
    opacity: 0;
    -webkit-transform: translateY(100%);
    transform: translateY(100%);
  }

  50% {
    opacity: 0;
    -webkit-transform: translateY(-100%);
    transform: translateY(-100%);
  }

  75% {
    opacity: 1;
    -webkit-transform: translateY(0%);
    transform: translateY(0%);
  }
}

@media (-moz-touch-enabled: 0), (hover: hover) {
  .RoundButton:hover {
    -webkit-transform: scale(1.1);
    transform: scale(1.1);
  }

  .RoundButton--small:hover {
    -webkit-transform: scale(1.15);
    transform: scale(1.15);
  }

  .RoundButton:not([aria-expanded="true"]):hover {
    color: $button-background;
  }

  .RoundButton[data-animate-left]:hover svg,
  .flickity-prev-next-button.previous:hover svg {
    -webkit-animation: buttonFromRightToLeft 0.5s ease-in-out forwards;
    animation: buttonFromRightToLeft 0.5s ease-in-out forwards;
  }

  .RoundButton[data-animate-right]:hover svg,
  .flickity-prev-next-button.next:hover svg {
    -webkit-animation: buttonFromLeftToRight 0.5s ease-in-out forwards;
    animation: buttonFromLeftToRight 0.5s ease-in-out forwards;
  }

  .RoundButton[data-animate-bottom]:hover svg {
    -webkit-animation: buttonFromTopToBottom 0.5s ease-in-out forwards;
    animation: buttonFromTopToBottom 0.5s ease-in-out forwards;
  }
}
/**
 * ----------------------------------------------------------------------------------------------
 * Flickity styles
 * ----------------------------------------------------------------------------------------------
 */

.flickity-enabled {
  position: relative;
}

body:not(.is-tabbing) .flickity-enabled:focus {
  outline: none;
}

.flickity-viewport {
  overflow: hidden;
  position: relative;
  height: auto;
}

.flickity-slider {
  position: absolute;
  width: 100%;
  height: 100%;
}

/* draggable */

.flickity-enabled {
  -webkit-tap-highlight-color: transparent;
}

.flickity-enabled.is-draggable {
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.flickity-enabled.is-draggable .flickity-viewport {
  cursor: -webkit-grab;
  cursor: grab;
}

.flickity-enabled.is-draggable .flickity-viewport.is-pointer-down {
  cursor: -webkit-grabbing;
  cursor: grabbing;
}

/* ---- previous/next buttons ---- */

.flickity-prev-next-button {
  @extend .RoundButton;
  position: absolute;

  &[disabled] {
    opacity: 0;
  }

  svg {
    width: auto;
    height: 18px;
    stroke-width: 1.5px;
    stroke: currentColor;
  }
}

/* ---- page dots ---- */

.flickity-page-dots {
  width: 100%;
  padding: 0;
  margin: 22px 0 0 0;
  list-style: none;
  text-align: center;
  line-height: 1;
}

.flickity-page-dots .dot {
  position: relative;
  display: inline-block;
  width: 9px;
  height: 9px;
  margin: 0 6px;
  border-radius: 50%;
  cursor: pointer;
  background: transparent;
  border: 1px solid $border-color;
  -webkit-transition: color 0.2s ease-in-out, background 0.2s ease-in-out;
  transition: color 0.2s ease-in-out, background 0.2s ease-in-out;

  /* This is used to increase the clickable area */
  &::before {
    position: absolute;
    content: '';
    top: -6px;
    right: -6px;
    left: -6px;
    bottom: -6px;
  }
}

.flickity-page-dots .dot.is-selected {
  background: currentColor;
  border-color: currentColor;
}

@include av-mq('tablet-and-up') {
  .flickity-page-dots .dot {
    width: 10px;
    height: 10px;
    margin: 0 7px;
    border-width: 2px;
  }
}

/**
 * ----------------------------------------------------------------------------------------------
 * Default styling for site-wide carousel
 * ----------------------------------------------------------------------------------------------
 */

.Carousel {
  position: relative;
}

.Carousel--fixed,
.Carousel--fixed .flickity-viewport,
.Carousel--fixed .Carousel__Cell {
  height: 100%;
}

/* This allows to hide cells that are not first one until slider is loaded */
.Carousel:not(.flickity-enabled) .Carousel__Cell:not(.is-selected) {
  display: none;
}

.Carousel__Cell {
  display: block;
  width: 100%;
}

.js .Carousel--fadeIn {
  .flickity-slider {
    -webkit-transform: none !important;
    transform: none !important;
  }

  .Carousel__Cell {
    left: 0 !important;
    opacity: 0;
    visibility: hidden;
    -webkit-transition: opacity 0.3s ease-in-out, visibility 0.3s ease-in-out;
    transition: opacity 0.3s ease-in-out, visibility 0.3s ease-in-out;
  }

  .Carousel__Cell.is-selected {
    opacity: 1;
    visibility: visible;
    -webkit-transition-delay: 0s;
    transition-delay: 0s;
  }
}

.Carousel--insideDots {
  .flickity-page-dots {
    position: absolute;
    width: auto;
    margin: 0;
    bottom: 24px;
    left: 20px;
  }

  .flickity-page-dots .dot {
    border-color: currentColor;
  }

  .flickity-page-dots .dot.is-selected {
    background: currentColor;
  }

  .flickity-prev-next-button {
    bottom: -25px;
    z-index: 1;
  }

  .flickity-prev-next-button.next {
    right: 25px;
  }

  .flickity-prev-next-button.previous {
    right: 75px;
    margin-right: 15px;
  }
}

@include av-mq('lap-and-up') {
  .Carousel--insideDots {
    .flickity-page-dots {
      bottom: 28px;
      right: 24px;
      left: auto;
    }
  }
}
/**
 * ----------------------------------------------------------------------------
 * Collapsible
 * ----------------------------------------------------------------------------
 */

.Collapsible {
  border-top: 1px solid $border-color;
  border-bottom: 1px solid $border-color;
  overflow: hidden;
}

.Collapsible + .Collapsible {
  border-top: none;
}

.Collapsible--padded {
  padding-left: 24px;
  padding-right: 24px;
}

.Collapsible__Button {
  display: block;
  position: relative;
  width: 100%;
  padding: 20px 0;
  text-align: left;
  cursor: pointer;
}

.Collapsible__Plus {
  position: absolute;
  right: 0;
  top: calc(50% - (11px / 2));
  width: 11px;
  height: 11px;

  &::before,
  &::after {
    position: absolute;
    content: '';
    top: 50%;
    left: 50%;
    -webkit-transform: translate(-50%, -50%) rotate(-90deg);
    transform: translate(-50%, -50%) rotate(-90deg);
    background-color: currentColor;
    -webkit-transition: opacity 0.4s ease-in-out, -webkit-transform 0.4s ease-in-out;
    transition: opacity 0.4s ease-in-out, -webkit-transform 0.4s ease-in-out;
    transition: transform 0.4s ease-in-out, opacity 0.4s ease-in-out;
    transition: transform 0.4s ease-in-out, opacity 0.4s ease-in-out, -webkit-transform 0.4s ease-in-out;
  }

  &::before {
    width: 11px;
    height: 1px;
    opacity: 1;
  }

  &::after {
    width: 1px;
    height: 11px;
  }
}

.Collapsible__Button[aria-expanded="true"] .Collapsible__Plus {
  &::before,
  &::after {
    -webkit-transform: translate(-50%, -50%) rotate(90deg);
    transform: translate(-50%, -50%) rotate(90deg);
  }

  &::before {
    opacity: 0;
  }
}

.Collapsible .Collapsible {
  margin-left: 16px;
  border: none;
}

.Collapsible .Collapsible .Collapsible__Button {
  padding: 13px 0;
}

.Collapsible__Inner {
  display: block;
  height: 0;
  visibility: hidden;
  -webkit-transition: height 0.35s ease-in-out, visibility 0s ease-in-out 0.35s;
  transition: height 0.35s ease-in-out, visibility 0s ease-in-out 0.35s;
}

.Collapsible__Button[aria-expanded="true"] + .Collapsible__Inner {
  visibility: visible;
  -webkit-transition: height 0.35s ease-in-out;
  transition: height 0.35s ease-in-out;
}

.Collapsible__Content {
  padding-bottom: 18px;
}

.Collapsible__Inner::before,
.Collapsible__Inner::after,
.Collapsible__Content::before,
.Collapsible__Content::after {
  content: '';
  display: table;
  clear: both;
}

.Collapsible .Linklist {
  margin-bottom: 4px;
}

.Collapsible .Linklist--bordered {
  margin-top: 16px;
  margin-bottom: 4px;
}

@include av-mq('tablet-and-up') {
  /* When this class is applied to a collapsible, it will display as a collapsible on mobile but not on larger screen, where it will
     automatically appear is auto-expanded */
  .Collapsible--autoExpand {
    border: none;
    overflow: visible;

    .Collapsible__Button {
      cursor: default;
      padding-top: 0;
      padding-bottom: 0;
      margin-bottom: 16px;
    }

    .Collapsible__Plus {
      display: none;
    }

    .Collapsible__Inner {
      height: auto;
      visibility: visible;
    }

    .Collapsible__Content {
      padding-bottom: 0;
    }

    .Linklist {
      margin-bottom: 0;
    }
  }

  .Collapsible--autoExpand {
    margin-bottom: 32px;
  }
}

@include av-mq('lap-and-up') {
  .Collapsible--padded {
    padding-left: 30px;
    padding-right: 30px;
  }

  .Collapsible--large .Collapsible__Button {
    padding: 34px 0;
  }

  .Collapsible--large .Collapsible__Content {
    padding-bottom: 45px;
  }
}
$drawer-header-height : 50px;

/**
 * ----------------------------------------------------------------------------
 * Base drawer
 * ----------------------------------------------------------------------------
 */

.Drawer {
  position: fixed;
  top: 0;
  left: 0;
  visibility: hidden;
  width: calc(100vw - 65px); /* Interestingly, 100% does not work on iOS 9 and lower */
  height: 100vh;
  max-height: none;
  z-index: 20;
  -webkit-transition: visibility 0.5s $drawer-transition-timing, -webkit-transform 0.5s $drawer-transition-timing;
  transition: visibility 0.5s $drawer-transition-timing, -webkit-transform 0.5s $drawer-transition-timing;
  transition: transform 0.5s $drawer-transition-timing, visibility 0.5s $drawer-transition-timing;
  transition: transform 0.5s $drawer-transition-timing, visibility 0.5s $drawer-transition-timing, -webkit-transform 0.5s $drawer-transition-timing;
  background: $background;
  -webkit-box-shadow: none;
  box-shadow: none;
  -ms-touch-action: manipulation;
  touch-action: manipulation;

  &:focus {
    outline: none;
  }

  /* Animating box-shadow is slow, even on modern browsers, so we instead move it in a pseudo-element and animate opacity */
  &::before {
    position: absolute;
    content: '';
    width: 100%;
    height: 100%;
    -webkit-box-shadow: 2px 0 10px rgba(#363636, 0.2), -2px 0 10px rgba(#363636, 0.2);
    box-shadow: 2px 0 10px rgba(#363636, 0.2), -2px 0 10px rgba(#363636, 0.2);
    opacity: 0;
    -webkit-transition: opacity 0.5s $drawer-transition-timing;
    transition: opacity 0.5s $drawer-transition-timing;
  }
}

.Drawer--secondary {
  background: $light-background;
}

.Drawer--fromLeft {
  -webkit-transform: translateX(calc(-100vw + 65px));
  transform: translateX(calc(-100vw + 65px));
}

.Drawer--fromRight {
  right: 0;
  left: auto;
  -webkit-transform: translateX(calc(100vw - 65px));
  transform: translateX(calc(100vw - 65px));
}

.Drawer[aria-hidden="false"] {
  visibility: visible;
  -webkit-transform: translateX(0);
  transform: translateX(0);

  &::before {
    opacity: 1;
  }
}

.Drawer__Container {
  width: 100%;

  .Drawer--fromLeft & {
    padding-left: 18px;
    padding-right: 24px;
  }

  .Drawer--fromRight & {
    padding-left: 24px;
    padding-right: 18px;
  }
}

.Drawer__Header {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  position: relative;
  height: $drawer-header-height;
  max-height: 60px;
  background: inherit;
  text-align: center;
  z-index: 1;

  @supports (--css: variables) {
    height: var(--header-height);
  }
}

.Drawer__Header--center {
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
}

.Drawer__Close {
  position: absolute;
  margin-left: 0;
  left: 18px;
  top: calc(50% - 7px);
  line-height: 0;

  svg {
    width: 15px;
    height: 15px;
    stroke-width: 1.25px;
  }
}

.Drawer--fromRight .Drawer__Close {
  right: 18px;
  left: auto;
}

.Drawer__Header--bordered {
  -webkit-box-shadow: 0 -1px $border-color inset;
  box-shadow: 0 -1px $border-color inset;
}

.Drawer--secondary .Drawer__Header--bordered {
  -webkit-box-shadow: 0 -1px rgba($border-color, 0.6) inset;
  box-shadow: 0 -1px rgba($border-color, 0.6) inset;
}

.Drawer--secondary .Collapsible {
  border-bottom-color: rgba($border-color, 0.6);
}

.Drawer__Content {
  position: relative;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  overflow: hidden;
  height: calc(100% - 60px);
  max-height: calc(100% - #{$drawer-header-height});

  @supports (--css: variables) {
    height: calc(100% - var(--header-height));
    max-height: calc(100% - var(--header-height));
  }

  /* This handles an edge case when the header is much bigger than the maximum size for content, but this only works on Safari as of today */
  @supports (width: calc(max(100%))) {
    height: calc(max(100% - var(--header-height), 100% - 60px));
    max-height: calc(max(100% - var(--header-height), 100% - 60px));
  }
}

.Drawer__Main {
  -webkit-box-flex: 1;
  -ms-flex: 1 1 auto;
  flex: 1 1 auto;
}

.Drawer__Footer {
  -webkit-box-flex: 0;
  -ms-flex: none;
  flex: none;
  -webkit-box-shadow: 0 -1px $border-color;
  box-shadow: 0 -1px $border-color;
}

.Drawer--secondary .Drawer__Footer {
  -webkit-box-shadow: 0 -1px rgba($border-color, 0.6);
  box-shadow: 0 -1px rgba($border-color, 0.6);
}

.Drawer__Footer--padded {
  padding: 24px;
}

@include av-mq('tablet-and-up') {
  .Drawer {
    width: 400px;
    -webkit-transform: translateX(-100%);
    transform: translateX(-100%);
  }

  .Drawer--small {
    width: 340px;
  }

  .Drawer--fromRight {
    -webkit-transform: translateX(100%);
    transform: translateX(100%);
  }

  .Drawer__Header {
    max-height: 80px;
    min-height: 60px;
  }

  .Drawer__Content {
    min-height: calc(100% - 80px);
    max-height: calc(100% - 80px);
  }

  .Drawer--fromLeft .Drawer__Container,
  .Drawer--fromRight .Drawer__Container {
    padding-left: 30px;
    padding-right: 30px;
  }

  .Drawer__Close {
    left: 30px;
  }

  .Drawer--fromRight .Drawer__Close {
    right: 30px;
    left: auto;
  }

  .Drawer__Close svg {
    stroke-width: 1.5px;
  }

  .Drawer__Footer--padded {
    padding: 24px 30px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Animation
 * ----------------------------------------------------------------------------
 */

[data-drawer-animated-left],
[data-drawer-animated-right] {
  opacity: 0;
  -webkit-transition: opacity 0.5s ease 0.25s, -webkit-transform 0.5s ease 0.25s;
  transition: opacity 0.5s ease 0.25s, -webkit-transform 0.5s ease 0.25s;
  transition: opacity 0.5s ease 0.25s, transform 0.5s ease 0.25s;
  transition: opacity 0.5s ease 0.25s, transform 0.5s ease 0.25s, -webkit-transform 0.5s ease 0.25s;

  .Drawer[aria-hidden="false"] & {
    opacity: 1;
    -webkit-transform: translateX(0);
    transform: translateX(0);
  }
}

[data-drawer-animated-left] {
  -webkit-transform: translateX(-65px);
  transform: translateX(-65px);
}

[data-drawer-animated-right] {
  -webkit-transform: translateX(65px);
  transform: translateX(65px);
}

[data-drawer-animated-bottom] {
  opacity: 0;
  -webkit-transform: translateY(45px);
  transform: translateY(45px);
  -webkit-transition: opacity 0.35s cubic-bezier(.25, .46, .45, .94), -webkit-transform 0.35s cubic-bezier(.25, .46, .45, .94);
  transition: opacity 0.35s cubic-bezier(.25, .46, .45, .94), -webkit-transform 0.35s cubic-bezier(.25, .46, .45, .94);
  transition: opacity 0.35s cubic-bezier(.25, .46, .45, .94), transform 0.35s cubic-bezier(.25, .46, .45, .94);
  transition: opacity 0.35s cubic-bezier(.25, .46, .45, .94), transform 0.35s cubic-bezier(.25, .46, .45, .94), -webkit-transform 0.35s cubic-bezier(.25, .46, .45, .94);

  .Drawer[aria-hidden="false"] & {
    opacity: 1;
    -webkit-transform: translateY(0);
    transform: translateY(0);
    -webkit-transition: opacity 0.25s cubic-bezier(.25, .46, .45, .94) 0.45s, -webkit-transform 0.25s cubic-bezier(.25, .46, .45, .94) 0.45s;
    transition: opacity 0.25s cubic-bezier(.25, .46, .45, .94) 0.45s, -webkit-transform 0.25s cubic-bezier(.25, .46, .45, .94) 0.45s;
    transition: opacity 0.25s cubic-bezier(.25, .46, .45, .94) 0.45s, transform 0.25s cubic-bezier(.25, .46, .45, .94) 0.45s;
    transition: opacity 0.25s cubic-bezier(.25, .46, .45, .94) 0.45s, transform 0.25s cubic-bezier(.25, .46, .45, .94) 0.45s, -webkit-transform 0.25s cubic-bezier(.25, .46, .45, .94) 0.45s;
  }
}
/**
 * ----------------------------------------------------------------------------
 * Basic form
 * ----------------------------------------------------------------------------
 */

.Form {
  width: 100%;
}

.Form__Item {
  position: relative;
  margin-bottom: 15px;
}

.Form__Input,
.Form__Textarea {
  -webkit-appearance: none;
  display: block;
  padding: 12px 14px;
  border-radius: 0;
  border: 1px solid $border-color;
  width: 100%;
  line-height: normal;
  resize: none;
  -webkit-transition: border-color 0.1s ease-in-out;
  transition: border-color 0.1s ease-in-out;
  background: transparent;

  &:focus {
    border-color: lighten($text-color, 25%);
    outline: none;
  }

  &::-webkit-input-placeholder {
    color: $text-color-light;
  }

  &:-ms-input-placeholder {
    color: $text-color-light;
  }

  &::placeholder {
    color: $text-color-light;
  }
}

.Form__FloatingLabel {
  position: absolute;
  bottom: calc(100% - 8px);
  left: 10px;
  padding: 0 5px;
  line-height: normal;
  color: $text-color-light;
  font-size: to-size(12px);
  opacity: 0;
  background: rgba($background, 0);
  pointer-events: none;
  -webkit-transform: translateY(3px);
  transform: translateY(3px);
  -webkit-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;
}

.Form__Input:not(:placeholder-shown) ~ .Form__FloatingLabel,
.Form__Textarea:not(:placeholder-shown) ~ .Form__FloatingLabel {
  opacity: 1;
  background: $background;
  -webkit-transform: translateY(0);
  transform: translateY(0);
}

.Form__Checkbox {
  position: absolute;
  opacity: 0;
}

.Form__Checkbox ~ label::before {
  display: inline-block;
  content: '';
  width: 1em;
  height: 1em;
  margin-right: 10px;
  border: 1px solid $border-color;
  vertical-align: -2px;
}

.Form__Checkbox ~ svg {
  position: absolute;
  top: 5px;
  left: 1px;
  width: 12px;
  height: 12px;
  -webkit-transform: scale(0);
  transform: scale(0);
  -webkit-transition: -webkit-transform 0.2s ease-in-out;
  transition: -webkit-transform 0.2s ease-in-out;
  transition: transform 0.2s ease-in-out;
  transition: transform 0.2s ease-in-out, -webkit-transform 0.2s ease-in-out;
  will-change: transform;
}

.Form__Checkbox:checked ~ label::before {
  border-color: $text-color;
}

.Form__Checkbox:checked ~ svg {
  -webkit-transform: scale(1);
  transform: scale(1);
}

.Form__Alert {
  margin-bottom: 20px;
}

.Form__Submit {
  display: block;
  margin-top: 20px;
}

.Form__Label {
  display: block;
  padding-bottom: 8px;
  font-size: to-size(11px);
  text-transform: uppercase;
  font-family: $heading-font-family;
  font-weight: $heading-font-weight;
  font-style: $heading-font-style;
  letter-spacing: 0.2em;
  line-height: normal;
}

.Form--small .Form__Input,
.Form--small .Form__Textarea {
  font-size: to-size(13px);
  padding-top: 10px;
  padding-bottom: 10px;
}

.Form--spacingTight {
  .Form__Item {
    margin-bottom: 15px;
  }

  .Form__Alert {
    margin-bottom: 20px;
  }
}

@include av-mq('tablet-and-up') {
  .Form__Item,
  .Form__Alert {
    margin-bottom: 30px;
  }

  .Form__Group {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
  }

  .Form__Group > .Form__Item {
    -webkit-box-flex: 1;
    -ms-flex: 1;
    flex: 1;
  }

  .Form__Group > :nth-child(2) {
    margin-left: 30px;
  }

  .Form--spacingTight {
    .Form__Group > :nth-child(2) {
      margin-left: 15px;
    }
  }
}

/**
 * ----------------------------------------------------------------------------
 * Form elements
 * ----------------------------------------------------------------------------
 */

.Form__Header {
  margin-bottom: 24px;
  text-align: center;
}

.Form__Hint {
  margin: 24px 0 0 0;
}

.Form__Hint:not(:last-child) {
  margin-bottom: 32px;
}

.Form__Hint--center {
  text-align: center;
}

.Form__ItemHelp {
  position: absolute;
  right: 12px;
  top: 50%;
  font-size: to-size(12px);
  color: $text-color-light;
  -webkit-transform: translateY(-50%);
  transform: translateY(-50%);
}

/**
 * ----------------------------------------------------------------------------
 * Styled select
 * ----------------------------------------------------------------------------
 */

select::-ms-expand {
  display: none;
}

.Select {
  position: relative;
  color: currentColor;
  line-height: 1;
  vertical-align: middle;
}

.Select svg {
  position: absolute;
  line-height: normal;
  pointer-events: none;
  vertical-align: baseline;
  fill: currentColor;
}

.Select select {
  /* Disable built-in styles */
  -webkit-appearance: none;
  -moz-appearance: none;

  display: inline-block;
  color: inherit;
  cursor: pointer;
  border-radius: 0;
  line-height: normal;

  /* Remove the ugly blue background on IE when a value is selected */
  &:focus::-ms-value {
    background: $background;
    color: $text-color;
  }
}

/* Make sure to have something easy to read... */
.Select option {
  background: white;
  color: black;
}

.Select--primary {
  &::after {
    content: '';
    position: absolute;
    right: 1px;
    top: 1px;
    height: calc(100% - 2px);
    width: 55px;
    background: -webkit-gradient(linear, left top, right top, from(rgba($background, 0)), color-stop(20%, rgba($background, 0.7)), color-stop(40%, $background));
    background: linear-gradient(to right, rgba($background, 0), rgba($background, 0.7) 20%, $background 40%);
    pointer-events: none;
  }

  select {
    width: 100%;
    height: 45px;
    padding-left: 14px;
    padding-right: 28px;
    border: 1px solid $border-color;
    background: $background;

    &:active, &:focus {
      border-color: $text-color;
      outline: none;
    }
  }

  svg {
    top: calc(50% - 5px);
    right: 15px;
    width: 10px;
    height: 10px;
    z-index: 1;
  }
}

.Select--transparent {
  select {
    padding-right: 15px;
    background: transparent;
    border: none;
    font-family: $heading-font-family;
    font-weight: $heading-font-weight;
    font-style: $heading-font-style;
    font-size: inherit;
    text-transform: uppercase;

    @if $uppercase-heading {
      letter-spacing: 0.2em;
    }
  }

  svg {
    top: calc(50% - 3px);
    right: 0;
    height: 6px;
  }
}
.HorizontalList {
  list-style: none;
  margin: -6px -8px;
}

.HorizontalList__Item {
  display: inline-block;
  margin: 6px 8px 6px 8px;
}

.HorizontalList__Item > .Link {
  display: inline-block;
}

.HorizontalList--spacingTight {
  margin-left: -8px;
  margin-right: -8px;
}

.HorizontalList--spacingTight .HorizontalList__Item {
  margin-right: 6px;
  margin-left: 6px;
}

.HorizontalList--spacingLoose {
  margin-left: -14px;
  margin-right: -14px;
}

.HorizontalList--spacingLoose .HorizontalList__Item {
  margin-right: 14px;
  margin-left: 14px;
}

.HorizontalList--spacingExtraLoose {
  margin-left: -17px;
  margin-right: -17px;
}

.HorizontalList--spacingExtraLoose .HorizontalList__Item {
  margin-right: 17px;
  margin-left: 17px;
}

.HorizontalList--spacingFill {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -ms-flex-pack: distribute;
  justify-content: space-around;
  -webkit-box-pack: space-evenly;
  -ms-flex-pack: space-evenly;
  justify-content: space-evenly;
}

.HorizontalList--spacingFill .HorizontalList__Item {
  margin-left: 0;
  margin-right: 0;
}

@include av-mq('desk') {
  .HorizontalList--spacingExtraLoose {
    margin-left: -21px;
    margin-right: -21px;
  }

  .HorizontalList--spacingExtraLoose .HorizontalList__Item {
    margin-right: 21px;
    margin-left: 21px;
  }
}
/**
 * This file contains various generic bloc to use with images
 */

/**
 * ----------------------------------------------------------------------------
 * Image overlay
 * ----------------------------------------------------------------------------
 */

.Image--contrast {
  position: relative;
}

.Image--contrast::after {
  position: absolute;
  content: '';
  width: 100%;
  height: 100%;
  left: 0;
  top: 0;
  background-image: -webkit-gradient(linear, left bottom, left top, from(rgba(#040404, 0.65)), to(rgba(#363636, 0.2)));
  background-image: linear-gradient(to top, rgba(#040404, 0.65), rgba(#363636, 0.2));
}

.Image--contrast > * {
  z-index: 1;
}

/**
 * ----------------------------------------------------------------------------
 * Image lazy loader (integrates with lazy sizes)
 * ----------------------------------------------------------------------------
 */

@-webkit-keyframes lazyLoader {
  0%, 100% {
    -webkit-transform: translateX(-50%);
    transform: translateX(-50%);
  }

  50% {
    -webkit-transform: translateX(100%);
    transform: translateX(100%);
  }
}

@keyframes lazyLoader {
  0%, 100% {
    -webkit-transform: translateX(-50%);
    transform: translateX(-50%);
  }

  50% {
    -webkit-transform: translateX(100%);
    transform: translateX(100%);
  }
}

.Image--fadeIn {
  opacity: 0;
  -webkit-transition: opacity 0.3s ease;
  transition: opacity 0.3s ease;
}

.Image--lazyLoaded.Image--fadeIn {
  opacity: 1;
}

@if $show-image-zooming {
  .Image--zoomOut {
    -webkit-transform: scale(1.1);
    transform: scale(1.1);
    opacity: 0;
    -webkit-transition: opacity 0.8s cubic-bezier(0.215, 0.61, 0.355, 1), -webkit-transform 0.8s cubic-bezier(0.215, 0.61, 0.355, 1);
    transition: opacity 0.8s cubic-bezier(0.215, 0.61, 0.355, 1), -webkit-transform 0.8s cubic-bezier(0.215, 0.61, 0.355, 1);
    transition: transform 0.8s cubic-bezier(0.215, 0.61, 0.355, 1), opacity 0.8s cubic-bezier(0.215, 0.61, 0.355, 1);
    transition: transform 0.8s cubic-bezier(0.215, 0.61, 0.355, 1), opacity 0.8s cubic-bezier(0.215, 0.61, 0.355, 1), -webkit-transform 0.8s cubic-bezier(0.215, 0.61, 0.355, 1);
  }

  .Image--lazyLoaded.Image--zoomOut {
    opacity: 1;
    -webkit-transform: none;
    transform: none;
  }
} @else {
  /* If zoom is disabled we apply the same effect than fadeIn */
  .Image--zoomOut {
    opacity: 0;
    -webkit-transition: opacity 0.3s ease;
    transition: opacity 0.3s ease;
  }

  .Image--lazyLoaded.Image--zoomOut {
    opacity: 1;
  }
}

.Image--slideRight,
.Image--slideLeft {
  -webkit-transform: translateX(25px);
  transform: translateX(25px);
  opacity: 0;
  -webkit-transition: opacity 0.8s cubic-bezier(0.215, 0.61, 0.355, 1), -webkit-transform 0.8s cubic-bezier(0.215, 0.61, 0.355, 1);
  transition: opacity 0.8s cubic-bezier(0.215, 0.61, 0.355, 1), -webkit-transform 0.8s cubic-bezier(0.215, 0.61, 0.355, 1);
  transition: transform 0.8s cubic-bezier(0.215, 0.61, 0.355, 1), opacity 0.8s cubic-bezier(0.215, 0.61, 0.355, 1);
  transition: transform 0.8s cubic-bezier(0.215, 0.61, 0.355, 1), opacity 0.8s cubic-bezier(0.215, 0.61, 0.355, 1), -webkit-transform 0.8s cubic-bezier(0.215, 0.61, 0.355, 1);
}

.Image--slideLeft {
  -webkit-transform: translateX(-25px);
  transform: translateX(-25px);
}

.Image--lazyLoaded.Image--slideRight,
.Image--lazyLoaded.Image--slideLeft {
  opacity: 1;
  -webkit-transform: translateX(0);
  transform: translateX(0);
}

.Image__Loader {
  position: absolute;
  display: block;
  height: 2px;
  width: 50px;
  left: 0;
  bottom: 0;
  right: 0;
  top: 0;
  opacity: 0;
  visibility: hidden;
  margin: auto;
  pointer-events: none;
  background-color: $border-color;
  z-index: -1;
  -webkit-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  overflow: hidden;
}

.Image__Loader::after {
  position: absolute;
  content: '';
  bottom: 0;
  right: 0;
  top: 0;
  height: 100%;
  width: 200%;
  background-color: $heading-color;
}

.Image--lazyLoading + .Image__Loader {
  opacity: 1;
  visibility: visible;
  z-index: 1;

  &::after {
    -webkit-animation: lazyLoader 3s infinite;
    animation: lazyLoader 3s infinite;
    -webkit-animation-timing-function: cubic-bezier(.43, .43, .25, .99);
    animation-timing-function: cubic-bezier(.43, .43, .25, .99);
  }
}

/**
 * ----------------------------------------------------------------------------
 * Aspect ratio
 * ----------------------------------------------------------------------------
 */

.AspectRatio {
  position: relative;
  margin-left: auto;
  margin-right: auto;

  &::before {
    content: '';
    display: block;
  }
}

.AspectRatio > img {
  max-height: 100%;
  max-width: 100%;
}

.AspectRatio--withFallback > img {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
}

.no-js .AspectRatio > img {
  display: none !important;
}

@supports (--css: variables) {
  /* For dynamic one, we use CSS variables, which makes it only compatible for newer browsers */

  .AspectRatio--withFallback {
    padding-bottom: 0 !important; /* For older browsers we use the padding-bottom trick, so make sure to remove it here */
  }

  .AspectRatio::before {
    padding-bottom: calc(100% / (var(--aspect-ratio)));
  }

  .AspectRatio > img,
  .no-js .AspectRatio > noscript img {
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
  }
}

.AspectRatio--square::before {
  padding-bottom: 100%;
}

.AspectRatio--short::before {
  padding-bottom: 75%;
}

.AspectRatio--tall::before {
  padding-bottom: 150%;
}

.AspectRatio--square > img,
.AspectRatio--short > img,
.AspectRatio--tall > img {
  position: absolute;
  width: auto;
  height: auto;
  left: 50%;
  top: 50%;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}

.Image--lazyLoad[data-sizes="auto"] {
  width: 100%; /* this is needed to help LazySizes calculate the correct size */
}
/**
 * ----------------------------------------------------------------------------
 * List
 * ----------------------------------------------------------------------------
 */

.Linklist {
  list-style: none;
  padding: 0;
}

.Linklist__Item {
  position: relative;
  display: block;
  margin-bottom: 12px;
  width: 100%;
  line-height: 1.5;
  text-align: left;
  -webkit-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;

  &:last-child {
    margin-bottom: 0 !important;
  }

  &::before {
    position: absolute;
    content: '';
    display: inline-block;
    width: 6px;
    height: 6px;
    top: calc(50% - 3px);
    left: 0;
    border-radius: 100%;
    background: $text-color;
    opacity: 0;
    -webkit-transition: opacity 0.1s ease-in-out;
    transition: opacity 0.1s ease-in-out;
  }
}

.Linklist__Item > .Link {
  display: block;
  width: 100%;
  text-align: inherit;
}

.Linklist--spacingLoose .Linklist__Item {
  margin-bottom: 18px;
}

.Linklist__Item.is-selected {
  padding-left: 18px;

  &::before {
    opacity: 1;
    -webkit-transition-delay: 0.1s;
    transition-delay: 0.1s;
  }
}

.Linklist--bordered {
  margin-left: 8px;
  padding: 0 20px 0 25px;
  border-left: 1px solid $border-color;
}

.Linklist--bordered li:first-child .Linklist__Item {
  margin-top: 2px;
}

.Linklist--bordered li:last-child .Linklist__Item {
  margin-bottom: 2px;
}
/**
 * Google map
 */

.FeaturedMap {
  max-width: 1150px;
  margin: 0 auto;
}

.FeaturedMap__MapContainer {
  position: relative;
  height: 240px;
  background-size: cover;
  background-position: center;
}

.FeaturedMap__GMap {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.FeaturedMap__Info {
  position: relative;
  margin: 0 auto;
  background: $light-background;
  text-align: left;
  z-index: 1;

  @if $light-background == $background {
    padding: 0 0 40px 0;
  } @else {
    padding: 25px;
  }
}

.FeaturedMap__Store {
  display: block;
  margin-bottom: 1.2em;
  font-family: $heading-font-family;
  font-weight: $heading-font-weight;
  font-style: $heading-font-style;
}

.FeaturedMap__Address {
  margin-bottom: 1.2em;
}

.FeaturedMap__Location {
  margin-top: 2.7em;
}

@include av-mq('tablet-and-up') {
  .FeaturedMap {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-orient: horizontal;
    -webkit-box-direction: reverse;
    -ms-flex-direction: row-reverse;
    flex-direction: row-reverse;
    -webkit-box-align: stretch;
    -ms-flex-align: stretch;
    align-items: stretch;
    padding-top: 0;
    height: 550px;
  }

  .FeaturedMap__MapContainer {
    -webkit-box-flex: 1;
    -ms-flex: 1 0 auto;
    flex: 1 0 auto;
    height: 100%;
  }

  .FeaturedMap__Info {
    -webkit-box-flex: 0;
    -ms-flex: none;
    flex: none;
    min-width: 370px;
    width: 370px;
    padding: 50px 60px;
  }
}
/**
 * ----------------------------------------------------------------------------
 * Anchor
 * ----------------------------------------------------------------------------
 */

.Anchor {
  display: block;
  position: relative;
  top: -75px;
  visibility: hidden;

  @supports (--css: variables) {
    top: calc(-1 * (var(--header-height))); /* + var(--announcement-bar-height)));*/
  }
}

/**
 * ----------------------------------------------------------------------------
 * Loading bar
 * ----------------------------------------------------------------------------
 */

.LoadingBar {
  position: fixed;
  top: 0;
  left: 0;
  height: 2px;
  width: 0;
  opacity: 0;
  background: $heading-color;
  -webkit-transition: width 0.25s ease-in-out;
  transition: width 0.25s ease-in-out;
  z-index: 50;
  pointer-events: none;
}

.LoadingBar.is-visible {
  opacity: 1;
}

@include av-mq('tablet-and-up') {
  .LoadingBar {
    height: 3px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Placeholder (used within the theme editor only)
 * ----------------------------------------------------------------------------
 */

.PlaceholderSvg {
  display: block;
  width: 100%;
  height: 100%;
  max-width: 100%;
  max-height: 100%;
}

.PlaceholderSvg--dark {
  background: dimgray;
  fill: #a1a1a1;
}

.PlaceholderBackground {
  position: absolute;
  height: 100%;
  width: 100%;
  top: 0;
  left: 0;
  z-index: -1;
  overflow: hidden;
  opacity: 0.7;
}

.PlaceholderBackground__Svg {
  height: 100% !important;
  width: auto !important;
  min-width: 100%;
}

/**
 * ----------------------------------------------------------------------------
 * Quantity selector
 * ----------------------------------------------------------------------------
 */

.QuantitySelector {
  display: -webkit-inline-box;
  display: -ms-inline-flexbox;
  display: inline-flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  border: 1px solid $border-color;
  white-space: nowrap;

  svg {
    width: 10px;
    height: 10px;
    stroke-width: 1.5px;
    vertical-align: -1px;
  }
}

.QuantitySelector__Button {
  display: inline-block;
  padding: 5px 9px; /* this allows to slightly increase the clickable area */
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.QuantitySelector__CurrentQuantity {
  display: inline-block;
  width: 20px;
  padding: 0;
  font-size: to-size(10px);
  text-align: center;
  letter-spacing: normal;
  background: transparent;
  border: none;
}

.QuantitySelector--large {
  .QuantitySelector__CurrentQuantity {
    width: 35px;
    font-size: to-size(14px);
  }

  .QuantitySelector__Button {
    padding: 10px 20px;
  }

  svg {
    width: 11px;
    height: 11px;
  }
}

@include av-mq('tablet-and-up') {
  .QuantitySelector__Button {
    padding: 7px 14px 8px 14px;
  }

  .QuantitySelector__CurrentQuantity {
    font-size: to-size(12px);
  }
}


/**
 * ----------------------------------------------------------------------------
 * Product price
 * ----------------------------------------------------------------------------
 */

.Price {
  display: inline-block;
}

.Price--highlight {
  color: $product-sale-price-color;
}

.Price--compareAt {
  position: relative;
  margin-left: 10px;

  &::before {
    position: absolute;
    content: '';
    top: 50%;
    left: -0.4em;
    width: calc(100% + 0.8em);
    height: 1px;
    background: currentColor;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Color swatch
 * ----------------------------------------------------------------------------
 */

.ColorSwatch {
  position: relative;
  display: inline-block;
  height: 30px;
  width: 30px;
  vertical-align: top;
  cursor: pointer;
  background-size: cover;
  outline-offset: 2px;

  &::after {
    content: '';
    position: absolute;
    width: calc(100% + 6px);
    height: calc(100% + 6px);
    top: -3px;
    left: -3px;
  }

  &:hover::after {
    border: 1px solid $border-color;
  }
}

.ColorSwatch--small {
  width: 16px;
  height: 16px;
}

.ColorSwatch.is-active::after,
.ColorSwatch__Radio:checked + .ColorSwatch::after {
  border: 1px solid currentColor !important;
}

.ColorSwatch__Radio {
  display: none;
}

.Collapsible .ColorSwatchList {
  padding-top: 4px;
  padding-bottom: 10px;
}

.Collapsible--autoExpand .ColorSwatchList {
  padding-top: 8px;
  padding-bottom: 12px;
}

/**
 * ----------------------------------------------------------------------------
 * Alerts
 * ----------------------------------------------------------------------------
 */

.Alert {
  display: block;
  padding: 10px 20px;
  white-space: normal;
  font-size: 1rem;
  word-break: break-all;
  word-break: break-word;
  text-shadow: none;
}

.Alert--large {
  padding: 18px 20px;
}

.Alert--error {
  background: #e4c4c4;
  color: #cb2b2b;
}

.Alert--success {
  background: #d2e4c4;
  color: #307a07;
}

.Alert__ErrorList {
  list-style: none;
}

@include av-mq('tablet-and-up') {
  .Alert--large {
    padding: 18px 30px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Segment
 * ----------------------------------------------------------------------------
 */

.Segment + .Segment {
  margin-top: 50px;
}

.Segment__Title {
  margin-bottom: 24px;
  padding-bottom: 10px;
  border-bottom: 1px solid $border-color;
  color: $text-color-light;
}

.Segment__Title--flexed {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
}

.Segment__ActionList {
  margin-top: 16px;
}

.Segment__ActionItem {
  line-height: 1.4;
}

.Segment__ActionItem + .Segment__ActionItem {
  margin-left: 20px;
}

.Segment__ButtonWrapper {
  margin-top: 32px;
}

@include av-mq('tablet-and-up') {
  .Segment__Title {
    margin-bottom: 34px;
  }

  .Segment__ActionList {
    margin-top: 24px;
  }
}

@include av-mq('desk') {
  .Segment + .Segment {
    margin-top: 65px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Empty state
 * ----------------------------------------------------------------------------
 */

.EmptyState {
  margin: 140px 0;
  text-align: center;
}

.EmptyState__Action {
  display: inline-block;
  margin-top: 20px;
}

@include av-mq('tablet-and-up') {
  .EmptyState {
    margin: 200px 0;
  }
}

@include av-mq('desk') {
  .EmptyState {
    margin: 250px 0;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Spinner
 * ----------------------------------------------------------------------------
 */

@-webkit-keyframes bouncingSpinnerAnimation {
  0%, 80%, 100% {
    -webkit-transform: scale(0);
    transform: scale(0);
  }

  40% {
    -webkit-transform: scale(1.0);
    transform: scale(1.0);
  }
}

@keyframes bouncingSpinnerAnimation {
  0%, 80%, 100% {
    -webkit-transform: scale(0);
    transform: scale(0);
  }

  40% {
    -webkit-transform: scale(1.0);
    transform: scale(1.0);
  }
}

.BouncingSpinner {
  display: block;
  text-align: center;
}

.BouncingSpinner > span {
  display: inline-block;
  width: 10px;
  height: 10px;
  background-color: currentColor;
  border-radius: 100%;
  -webkit-animation: bouncingSpinnerAnimation 1.4s infinite ease-in-out both;
  animation: bouncingSpinnerAnimation 1.4s infinite ease-in-out both;
}

.BouncingSpinner > span:first-child {
  -webkit-animation-delay: -0.32s;
  animation-delay: -0.32s;
}

.BouncingSpinner > span:nth-child(2) {
  -webkit-animation-delay: -0.16s;
  animation-delay: -0.16s;
}

/**
 * ----------------------------------------------------------------------------
 * Video
 * ----------------------------------------------------------------------------
 */

.Video__PlayButton {
  display: inline-block;
  -webkit-transition: -webkit-transform 0.2s ease-in-out;
  transition: -webkit-transform 0.2s ease-in-out;
  transition: transform 0.2s ease-in-out;
  transition: transform 0.2s ease-in-out, -webkit-transform 0.2s ease-in-out;
  height: 80px;
  width: 80px;
  cursor: pointer;
  -webkit-filter: drop-shadow(0 2px 2px rgba(#000000, 0.2));
  filter: drop-shadow(0 2px 2px rgba(#000000, 0.2));

  @media (-moz-touch-enabled: 0), (hover: hover) {
    &:hover {
      -webkit-transform: scale(1.1);
      transform: scale(1.1);
    }
  }
}

.Video__PlayButton svg {
  width: 80px;
  height: 80px;
  pointer-events: none;
}

.VideoWrapper {
  position: relative;
  padding-bottom: 56.25%;
  height: 0;
  overflow: hidden;
  max-width: 100%;
}

.VideoWrapper iframe,
.VideoWrapper object,
.VideoWrapper embed {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

/**
 * ----------------------------------------------------------------------------
 * Announcement bar
 * ----------------------------------------------------------------------------
 */

.AnnouncementBar {
  position: relative;
  text-align: center;
  font-size: to-size(10px);
  z-index: 1;
}

.AnnouncementBar__Wrapper {
  padding: 12px 15px;
}

.AnnouncementBar__Content {
  color: inherit;
  margin: 0;
}

@include av-mq('tablet-and-up') {
  .AnnouncementBar {
    font-size: to-size(11px);
  }
}

/**
 * ----------------------------------------------------------------------------
 * Share buttons
 * ----------------------------------------------------------------------------
 */

.ShareButtons {
  display: table;
  table-layout: fixed;
  border-collapse: collapse;
  width: 100%;
}

.ShareButtons__Item {
  display: table-cell;
  width: 60px;
  height: 45px;
  min-height: 45px;
  color: $text-color-light;
  text-align: center;
  vertical-align: middle;
  background: $background;
  border: 1px solid $border-color;
  outline: 1px solid transparent;
  outline-offset: -1px;
  -webkit-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;

  svg {
    height: 18px;
    width: 18px;
    vertical-align: text-bottom;
  }
}

.ShareButtons__Item--facebook:hover,
.no-supports-hover .ShareButtons__Item--facebook {
  background: #4469af;
  color: #ffffff;
  border-color: #4469af;
  outline: 1.5px solid #4469af;
}

.ShareButtons__Item--pinterest:hover,
.no-supports-hover .ShareButtons__Item--pinterest {
  background: #c8232c;
  color: #ffffff;
  border-color: #c8232c;
  outline: 1.5px solid #c8232c;
}

.ShareButtons__Item--twitter:hover,
.no-supports-hover .ShareButtons__Item--twitter {
  background: #00aced;
  color: #ffffff;
  border-color: #00aced;
  outline: 1.5px solid #00aced;
}

@include av-mq('tablet-and-up') {
  .ShareButtons {
    width: auto;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Featured quote
 * ----------------------------------------------------------------------------
 */

.FeaturedQuote {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  padding: 120px 40px;
  background: $secondary-elements-background;
  color: $secondary-elements-text-color;
  font-size: to-size(18px);
}

.FeaturedQuote__Author {
  margin-top: 14px;
  font-size: to-size(14px);
  opacity: 0.5;
}

@include av-mq('lap-and-up') {
  .FeaturedQuote {
    padding-top: 40px;
    padding-bottom: 40px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Shopify CAPTCHA
 * ----------------------------------------------------------------------------
 */

.shopify-challenge__container {
  margin-top: 80px;
  margin-bottom: 80px;
  text-align: center;
}

.shopify-challenge__container .shopify-challenge__button {
  position: relative;
  display: inline-block;
  padding: 14px 28px;
  line-height: normal;
  border: 1px solid transparent;
  border-radius: 0;
  text-transform: uppercase;
  font-size: to-size(12px);
  text-align: center;
  letter-spacing: 0.2em;
  font-family: $heading-font-family;
  font-weight: $heading-font-weight;
  font-style: $heading-font-style;
  background: $button-background;
  color: $button-text-color;
}


/**
 * ----------------------------------------------------------------------------
 * Newsletter (home page)
 * ----------------------------------------------------------------------------
 */

.ImageHero--newsletter .SectionHeader.SectionHeader {
  margin-bottom: 30px;
}

.Newsletter .Form__Input::-webkit-input-placeholder {
  color: inherit;
}

.Newsletter .Form__Input:-ms-input-placeholder {
  color: inherit;
}

.Newsletter .Form__Input::placeholder {
  color: inherit;
}

.Newsletter .Form__Input:focus {
  border-color: currentColor;
}

.Newsletter .Form__Submit {
  width: 100%;
}

@include av-mq('phone') {
  .ImageHero--newsletter {
    min-height: 450px !important;
  }

  .ImageHero--newsletter .ImageHero__ContentOverlay {
    padding-left: 25px;
    padding-right: 25px;
  }
}

@include av-mq('tablet-and-up') {
  .Newsletter__Inner {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
  }

  .Newsletter .Form__Input {
    min-width: 395px;
    width: 395px;
  }

  .Newsletter .Form__Submit {
    margin: 0 0 0 20px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * TOOLTIP
 * ----------------------------------------------------------------------------
 */

@media (-moz-touch-enabled: 0), (hover: hover) {
  [data-tooltip] {
    position: relative;

    &::before {
      position: absolute;
      content: attr(data-tooltip);
      bottom: 70%;
      left: 70%;
      padding: 4px 11px 3px 11px;
      white-space: nowrap;
      border: 1px solid $border-color;
      background: $light-background;
      color: $text-color-light;
      font-size: to-size(13px);
      pointer-events: none;
      visibility: hidden;
      opacity: 0;
      -webkit-transition: visibility 0.2s ease-in-out, opacity 0.2s ease-in-out;
      transition: visibility 0.2s ease-in-out, opacity 0.2s ease-in-out;
      z-index: 1;
    }

    &:hover::before {
      opacity: 1;
      visibility: visible;
    }
  }
}
.Modal {
  position: fixed;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  visibility: hidden;
  top: 50%;
  left: 50%;
  width: 480px;
  max-width: calc(100vw - 40px);
  max-height: calc(100vh - 40px);
  padding: 15px 20px 20px 20px;
  z-index: 20;
  opacity: 0;
  overflow: auto;
  -webkit-overflow-scrolling: touch;
  background: $background;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  -webkit-transition: opacity 0.3s ease-in-out, visibility 0.3s ease-in-out;
  transition: opacity 0.3s ease-in-out, visibility 0.3s ease-in-out;

  @supports (--css: variables) {
    max-height: calc(var(--window-height) - 40px);
  }
}

.Modal[aria-hidden="false"] {
  visibility: visible;
  opacity: 1;
}

.Modal--dark {
  background: $secondary-elements-background;
  color: $secondary-elements-text-color;

  .Rte h1,
  .Rte h2,
  .Rte h3,
  .Rte h4,
  .Rte h5,
  .Rte h6 {
    color: $secondary-elements-text-color;
  }
}

.Modal--fullScreen {
  max-width: none;
  max-height: none;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  -webkit-transform: none;
  transform: none;
}

.Modal--pageContent {
  padding: 60px 0 50px 0;
}

.Modal--videoContent {
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  background: #000000; /* Full theatre experience ! */
  color: #ffffff;
}

.Modal .Heading:not(.Link) {
  color: inherit;
}

.Modal__Header {
  margin-bottom: 30px;
  text-align: center;
}

.Modal__Close {
  display: block;
  margin: 25px auto 0 auto;
  -ms-flex-negative: 0;
  flex-shrink: 0;
}

.Modal__Close--outside {
  position: absolute;
  margin-top: 0;
  top: 20px;
  right: 20px;
  line-height: 0;
  opacity: 0.5;
  -webkit-transition: opacity 0.2s ease-in-out;
  transition: opacity 0.2s ease-in-out;

  &:hover {
    opacity: 1;
  }

  svg {
    height: 16px;
    width: 16px;
    stroke-width: 1.25px;
  }
}

.Modal--fullScreen .Modal__Close--outside {
  right: 40px;
  top: 40px;
}

.Modal__Content iframe {
  display: none;
}

.Modal[aria-hidden="false"] .Modal__Content iframe {
  display: block;
}

/* We override some styles for common elements like table */

.Modal__Content {
  th,
  td {
    border-color: $secondary-elements-border-color !important;
  }

  thead th:empty,
  tbody th {
    background: $secondary-elements-background !important;
  }
}

@include av-mq('tablet-and-up') {
  .Modal:not(.Modal--pageContent) {
    padding: 35px 40px 40px 40px;
  }
}

@include av-mq('lap-and-up') {
  .Modal {
    -webkit-box-orient: vertical;
    -webkit-box-direction: normal;
    -ms-flex-direction: column;
    flex-direction: column;
  }

  .Modal--pageContent {
    padding: 100px 0 80px 0;
  }

  .Modal--pageContent .Modal__Content {
    -webkit-box-flex: 1;
    -ms-flex: 1 0 0px;
    flex: 1 0 0;
  }

  .Modal__Close:not(.Modal__Close--outside) {
    margin-top: 40px;
    -ms-flex-negative: 0;
    flex-shrink: 0;
  }
}
/**
 * ----------------------------------------------------------------------------
 * A11Y
 * ----------------------------------------------------------------------------
 */

.PageSkipLink:focus {
  clip: auto;
  width: auto;
  height: auto;
  margin: 0;
  color: $text-color;
  background-color: $background;
  padding: 10px;
  z-index: 10000;
  -webkit-transition: none;
  transition: none;
}

/**
 * ----------------------------------------------------------------------------
 * Page overlay
 * ----------------------------------------------------------------------------
 */

.PageOverlay {
  position: fixed;
  top: 0;
  left: 0;
  height: 100vh;
  width: 100vw;
  z-index: 10;
  visibility: hidden;
  opacity: 0;
  background: #363636;
  -webkit-transition: opacity 0.3s ease-in-out, visibility 0.3s ease-in-out;
  transition: opacity 0.3s ease-in-out, visibility 0.3s ease-in-out;
}

.PageOverlay.is-visible {
  opacity: 0.5;
  visibility: visible;
}

/**
 * ----------------------------------------------------------------------------
 * Page header
 * ----------------------------------------------------------------------------
 */

.PageHeader {
  position: relative;
  margin: 35px 0;
}

.PageHeader--withBackground {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  margin: 0;
  width: 100%;
  min-height: 450px;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  background-size: cover;
  color: #ffffff;
  overflow: hidden;
}

.PageHeader--withBackground .Heading,
.PageHeader--withBackground .Rte a:not(.Button) {
  color: #ffffff;
  -webkit-text-decoration-color: #ffffff;
  text-decoration-color: #ffffff;
}

.PageHeader__ImageWrapper {
  position: absolute;
  height: 100%;
  width: 100%;
  top: 0;
  left: 0;
  background-size: cover;
  background-position: center center;

  @supports (--css: variables) {
    top: calc(-1 * var(--announcement-bar-height, 0px));
    height: calc(100% + var(--announcement-bar-height, 0px));
  }
}

.PageHeader .SectionHeader__Heading,
.PageHeader .SectionHeader__Description {
  margin-top: 0 !important;
}

.PageHeader .Alert {
  margin-top: 22px;
}

.PageHeader__Back {
  display: inline-block;
  margin-bottom: 25px;

  svg {
    height: 9px;
    margin-right: 12px;
    vertical-align: initial;
  }
}

/* Double selector is just to increase specificity and avoid !important */

.PageHeader--withBackground .SectionHeader.SectionHeader {
  position: relative;
  padding: 60px 0 80px 0;

  @supports (--css: variables) {
    margin-top: calc(var(--header-height) * var(--header-is-transparent, 0));
  }
}

@include av-mq('phone') {
  .PageHeader .SectionHeader__Heading {
    margin-bottom: 10px;
  }
}

@include av-mq('tablet-and-up') {
  .PageHeader {
    margin: 50px 0;
  }

  .PageHeader--withBackground {
    min-height: 450px;
    margin-top: 0;
    margin-bottom: 0;

    @supports (--css: variables) {
      min-height: calc(380px + var(--header-height) * var(--header-is-transparent, 0));
    }
  }

  .PageHeader--small.PageHeader--withBackground {
    min-height: 420px;

    @supports (--css: variables) {
      min-height: calc(350px + var(--header-height) * var(--header-is-transparent, 0));
    }
  }

  .PageHeader--large.PageHeader--withBackground {
    min-height: 480px;

    @supports (--css: variables) {
      min-height: calc(410px + var(--header-height) * var(--header-is-transparent, 0));
    }
  }

  .PageHeader--withBackground .SectionHeader.SectionHeader {
    margin-top: 50px;
    padding: 40px 0;

    @supports (--css: variables) {
      margin-top: calc(var(--header-height) * var(--header-is-transparent, 0));
    }
  }
}

@include av-mq('desk') {
  .PageHeader--withBackground {
    min-height: 550px;

    @supports (--css: variables) {
      min-height: calc(450px + var(--header-height) * var(--header-is-transparent, 0));
    }
  }

  .PageHeader--small.PageHeader--withBackground {
    min-height: 500px;

    @supports (--css: variables) {
      min-height: calc(400px + var(--header-height) * var(--header-is-transparent, 0));
    }
  }

  .PageHeader--large.PageHeader--withBackground {
    min-height: 620px;

    @supports (--css: variables) {
      min-height: calc(520px + var(--header-height) * var(--header-is-transparent, 0));
    }
  }
}

@media screen and (min-width: 1800px) {
  .PageHeader--withBackground {
    min-height: 650px;

    @supports (--css: variables) {
      min-height: calc(600px + var(--header-height) * var(--header-is-transparent, 0));
    }
  }

  .PageHeader--small.PageHeader--withBackground {
    min-height: 600px;

    @supports (--css: variables) {
      min-height: calc(550px + var(--header-height) * var(--header-is-transparent, 0));
    }
  }

  .PageHeader--large.PageHeader--withBackground {
    min-height: 700px;

    @supports (--css: variables) {
      min-height: calc(650px + var(--header-height) * var(--header-is-transparent, 0));
    }
  }
}

/**
 * ----------------------------------------------------------------------------
 * Page layout (to create two columns) and content
 * ----------------------------------------------------------------------------
 */

.PageLayout__Section:first-child {
  margin-bottom: 60px;
}

.PageLayout__Section--sticky {
  position: -webkit-sticky;
  position: sticky;
  top: 75px;
  -ms-flex-item-align: start;
  align-self: flex-start;

  @supports (--css: variables) {
    top: calc(var(--header-height) + 20px);
  }
}

@include av-mq('tablet-and-up') {
  .PageLayout {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -ms-flex-wrap: nowrap;
    flex-wrap: nowrap;
  }

  .PageLayout__Section {
    -webkit-box-flex: 1;
    -ms-flex: 1 0 0px;
    flex: 1 0 0;
  }

  .PageLayout__Section:first-child {
    margin-bottom: 0;
  }

  .PageLayout__Section--secondary {
    -webkit-box-flex: 1;
    -ms-flex: 1 1 200px;
    flex: 1 1 200px;
    max-width: 200px;
  }

  .PageLayout__Section + .PageLayout__Section {
    margin-left: 50px;
  }
}

@include av-mq('tablet') {
  .PageLayout--breakLap {
    display: block;
  }

  .PageLayout--breakLap .PageLayout__Section:first-child {
    margin-bottom: 60px;
  }

  .PageLayout--breakLap .PageLayout__Section + .PageLayout__Section {
    margin-left: 0;
    width: 100%;
  }
}

@include av-mq('lap-and-up') {
  .PageLayout__Section--secondary {
    -ms-flex-preferred-size: 235px;
    flex-basis: 235px;
    max-width: 235px;
  }
}

@include av-mq('desk') {
  .PageLayout__Section + .PageLayout__Section {
    margin-left: 80px;
  }

  .PageLayout__Section--secondary {
    -ms-flex-preferred-size: 290px;
    flex-basis: 290px;
    max-width: 290px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Page content
 * ----------------------------------------------------------------------------
 */

.PageContent {
  max-width: 1000px;
  margin: 35px auto;
}

.PageContent--fitScreen {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  min-height: calc(100vh - 120px);
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;

  @supports (--css: variables) {
    min-height: calc(var(--window-height) - var(--header-height) - var(--announcement-bar-height, 0px) - 120px); /* 120px is the margin */
  }
}

.PageContent--narrow {
  max-width: 680px;
}

.PageContent--extraNarrow {
  max-width: 400px;
}

.PageHeader + .PageContent {
  margin-top: 0;
}

@include av-mq('tablet-and-up') {
  .PageContent {
    margin-bottom: 80px;
    margin-top: 80px;
  }

  .PageContent--fitScreen {
    min-height: calc(100vh - 160px);

    @supports (--css: variables) {
      min-height: calc(var(--window-height) - var(--header-height) - var(--announcement-bar-height, 0px) - 160px); /* 160px is the margin */
    }
  }
}
.Pagination {
  margin: 60px 0;
  text-align: center;
  font-family: $heading-font-family;
  font-weight: $heading-font-weight;
  font-style: $heading-font-style;
  font-size: to-size(12px);
  line-height: 1;
}

.Pagination__Nav {
  display: inline-block;
  list-style: none;
}

.Pagination__NavItem {
  display: inline-block;
  padding: 16px 20px;
  border-bottom: 1px solid $border-color;

  svg {
    width: 6px;
    height: 10px;
    vertical-align: -1px;
  }
}

.Pagination__NavItem.is-active {
  color: $text-color;
  border-bottom-color: $text-color;
  -webkit-box-shadow: 0 -2px $text-color inset;
  box-shadow: 0 -2px $text-color inset;
}

@include av-mq('tablet-and-up') {
  .Pagination {
    margin: 80px 0;
  }

  .Pagination__NavItem {
    padding-left: 28px;
    padding-right: 28px;
  }
}

@include av-mq('desk') {
  .Pagination {
    margin: 120px 0;
  }
}
.Panel {
  position: relative;
  border: 1px solid $border-color;
  padding: 60px 24px;
}

.Panel--withArrows {
  margin: 0 15px;
}

.Panel--flush {
  padding-left: 0 !important;
  padding-right: 0 !important;
}

.Panel__Title {
  position: absolute;
  top: 0;
  left: 50%;
  margin: 0;
  padding: 0 14px 0 18px;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  background: $background;
  white-space: nowrap;
}

.Panel .flickity-prev-next-button {
  top: calc(50% - (45px / 2));
}

.Panel .flickity-prev-next-button.next {
  right: calc(-45px / 2);
}

.Panel .flickity-prev-next-button.previous {
  left: calc(-45px / 2);
}

@include av-mq('tablet-and-up') {
  .Panel {
    padding-left: 50px;
    padding-right: 50px;
  }

  .Panel--withArrows {
    margin-left: 0;
    margin-right: 0;
  }
}
.Popover {
  position: fixed;
  width: 100%;
  bottom: 0;
  left: 0;
  background: $light-background;
  z-index: 10;
  -webkit-box-shadow: 0 -2px 10px rgba(#363636, 0.2);
  box-shadow: 0 -2px 10px rgba(#363636, 0.2);
  -ms-touch-action: manipulation;
  touch-action: manipulation;
  -webkit-transform: translateY(100%);
  transform: translateY(100%);
  visibility: hidden;
  -webkit-transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  transition: all 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
}

.Popover--secondary {
  background: $background;
}

.Popover[aria-hidden="false"] {
  -webkit-transform: translateY(0);
  transform: translateY(0);
  visibility: visible;
}

.Popover__Header {
  position: relative;
  padding: 13px 20px;
  border-bottom: 1px solid rgba($border-color, 0.4);
  text-align: center;
}

.Popover__Close {
  position: absolute;
  left: 20px;
  top: calc(50% - 7px);
  line-height: 0;

  svg {
    stroke-width: 1.1px;
  }
}

.Popover__ValueList {
  list-style: none;
  max-height: 385px;
  padding: 18px 0;
  overflow: auto;
  -webkit-overflow-scrolling: touch;
}

.Popover__Value {
  display: block;
  padding: 12px 20px;
  width: 100%;
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  color: $text-color-light;
  text-align: center;
  -webkit-transition: color 0.2s ease-in-out;
  transition: color 0.2s ease-in-out;

  &:focus {
    background: $background;
    outline: none;
  }
}

.Popover__Value.is-selected {
  color: $text-color;
}

.Popover__FooterHelp {
  width: 100%;
  padding: 18px 20px;
  text-align: center;
  border-top: 1px solid rgba($border-color, 0.4);
}

@include av-mq('lap-and-up') {
  .Popover {
    -webkit-transform: none;
    transform: none;
    width: auto;
    bottom: auto;
    left: auto;
    opacity: 0;
    -webkit-transition: opacity 0.2s ease-in-out, visibility 0.2s ease-in-out;
    transition: opacity 0.2s ease-in-out, visibility 0.2s ease-in-out;

    &::before {
      content: '';
      position: absolute;
      right: 40px;
      width: 10px;
      height: 10px;
      border-style: solid;
    }
  }

  .Popover--withMinWidth {
    min-width: 375px;
  }

  .Popover--positionBottom::before {
    bottom: 100%;
    border-width: 0 10px 10px 10px;
    border-color: transparent transparent $light-background transparent;
    -webkit-filter: drop-shadow(0 -2px 2px rgba(#363636, 0.2));
    filter: drop-shadow(0 -2px 2px rgba(#363636, 0.2));
  }

  .Popover--positionTop::before {
    top: 100%;
    border-width: 10px 10px 0 10px;
    border-color: $light-background transparent transparent transparent;
    -webkit-filter: drop-shadow(0 2px 2px rgba(#363636, 0.2));
    filter: drop-shadow(0 2px 2px rgba(#363636, 0.2));
  }

  .Popover--positionLeft::before {
    left: 100%;
    border-width: 10px 0 10px 10px;
    border-color: transparent transparent transparent $light-background;
    -webkit-filter: drop-shadow(2px 0 2px rgba(#363636, 0.2));
    filter: drop-shadow(2px 0 2px rgba(#363636, 0.2));
  }

  .Popover--positionLeft.Popover--alignCenter::before {
    top: calc(50% - 10px);
  }

  .Popover--positionLeft.Popover--alignBottom::before {
    top: 15px;
  }

  .Popover--positionLeft.Popover--alignTop::before {
    bottom: 10px;
  }

  .Popover[aria-hidden="false"] {
    opacity: 1;
    -webkit-transform: none;
    transform: none;
  }

  .Popover__Header {
    display: none;
  }

  .Popover__Value {
    padding-left: 50px;
    padding-right: 50px;
    text-align: right;
  }

  .Popover--withMinWidth .Popover__Value {
    text-align: center;
  }
}
.Rte {
  iframe {
    max-width: 100%;
  }

  img {
    display: block;
    margin: 0 auto;
  }

  a:not(.Button) {
    color: $link-color;
    text-decoration: underline;
    -webkit-text-decoration-color: rgba($link-color, 0.6);
    text-decoration-color: rgba($link-color, 0.6);
    text-underline-position: under;
    -webkit-transition: color 0.2s ease-in-out, -webkit-text-decoration-color 0.2s ease-in-out;
    transition: color 0.2s ease-in-out, -webkit-text-decoration-color 0.2s ease-in-out;
    transition: color 0.2s ease-in-out, text-decoration-color 0.2s ease-in-out;
    transition: color 0.2s ease-in-out, text-decoration-color 0.2s ease-in-out, -webkit-text-decoration-color 0.2s ease-in-out;

    &:hover {
      color: $text-color;
      -webkit-text-decoration-color: rgba($text-color, 0.6);
      text-decoration-color: rgba($text-color, 0.6);
    }
  }

  p:not(:last-child),
  ul:not(:last-child),
  ol:not(:last-child) {
    margin-bottom: 1.6em;
  }

  img,
  blockquote,
  .VideoWrapper,
  .Form {
    margin-top: 2.4em;
    margin-bottom: 2.4em;
  }

  ul, ol {
    margin-left: 30px;
    padding-left: 0;
    list-style-position: outside;
  }

  li {
    padding: 5px 0;
  }

  h1,
  h2,
  h3,
  h4,
  h5,
  h6 {
    font-family: $heading-font-family;
    font-weight: $heading-font-weight;
    font-style: $heading-font-style;
    color: $heading-color;
    -webkit-transition: color 0.2s ease-in-out;
    transition: color 0.2s ease-in-out;

    @if $uppercase-heading {
      letter-spacing: 0.2em;
      text-transform: uppercase;
    }
  }

  h1 {
    @extend .u-h1;
    margin: 2.2em 0 0.8em;
  }

  h2 {
    @extend .u-h2;
    margin: 2.2em 0 0.9em;
  }

  h3 {
    @extend .u-h3;
    margin: 2.2em 0 1.2em;
  }

  h4 {
    @extend .u-h4;
    margin: 2.2em 0 1.4em;
  }

  h5 {
    @extend .u-h5;
    margin: 2.2em 0 1.6em;
  }

  h6 {
    @extend .u-h6;
    margin: 2.2em 0 1.8em;
  }

  blockquote {
    margin-left: 0;
    padding: 6px 0 6px 40px;
    font-size: 1.15em;
    line-height: 1.75;
    border-left: 3px solid rgba($border-color, 0.6);
  }

  table {
    @extend .Table;
  }

  p:last-child,
  blockquote:last-child,
  ul:last-child,
  ol:last-child,
  h1:last-child,
  h2:last-child,
  h3:last-child,
  h4:last-child,
  h5:last-child,
  h6:last-child {
    margin-bottom: 0;
  }
}

@include av-mq('lap-and-up') {
  .Rte {
    img,
    .VideoWrapper,
    .Form {
      margin-top: 3em;
      margin-bottom: 3em;
    }

    blockquote {
      margin-left: 40px;
    }
  }
}
.shopify-section--hidden {
  display: none;
}

.shopify-section--bordered + .shopify-section--bordered {
  border-top: 1px solid $border-color;
}

/* When a spacing is applied to a bordered section, as it is isolated, we use padding, otherwise margin */

.Section--spacingNormal {
  margin: 50px 0;
}

.Section--spacingLarge,
.Section--spacingExtraLarge {
  margin: 90px 0;
}

.shopify-section--bordered > .Section--spacingNormal {
  padding: 50px 0;
  margin-top: 0;
  margin-bottom: 0;
}

.shopify-section--bordered > .Section--spacingLarge,
.shopify-section--bordered > .Section--spacingExtraLarge {
  padding: 90px 0;
  margin-top: 0;
  margin-bottom: 0;
}

.SectionHeader:not(:only-child) {
  margin-bottom: 40px;
}

.SectionHeader--center {
  text-align: center;
}

/*
  This is just a hack to slightly increase the selector specificity. What this does is actually taking into account the line height (1.65)
  and removing the remaining amount in both direction (0.65 / 2 => 0.325) to have more easier and consistent alignments
*/

.SectionHeader__Heading.SectionHeader__Heading,
.SectionHeader__SubHeading.SectionHeader__SubHeading {
  margin-top: -0.325em;
}

.SectionHeader__SubHeading + .SectionHeader__Heading,
.SectionHeader__SubHeading + .SectionHeader__TabList,
.SectionHeader__Description {
  margin-top: 16px;
}

.SectionHeader__Description {
  max-width: 530px;
}

.SectionHeader__Description a {
  text-decoration: underline;
  -webkit-text-decoration-color: currentColor;
  text-decoration-color: currentColor;
  text-underline-position: under;
}

.SectionHeader--center .SectionHeader__Description {
  margin-left: auto;
  margin-right: auto;
}

.SectionHeader__ButtonWrapper {
  margin-top: 20px;
}

.SectionHeader__IconHolder {
  margin-top: 30px;
}

/* The SectionFooter is usually use at the end of a given section to redirect somewhere else */
.SectionFooter {
  margin-top: 50px;
  text-align: center;
}

@include av-mq('tablet-and-up') {
  .SectionHeader__Heading--emphasize {
    font-size: to-size(22px);
  }
}

@include av-mq('lap-and-up') {
  .Section--spacingNormal {
    margin: 80px 0;
  }

  .Section--spacingLarge {
    margin: 120px 0;
  }

  .Section--spacingExtraLarge {
    margin: 145px 0;
  }

  .shopify-section--bordered > .Section--spacingNormal {
    padding: 80px 0;
  }

  .shopify-section--bordered > .Section--spacingLarge {
    padding: 120px 0;
  }

  .shopify-section--bordered > .Section--spacingExtraLarge {
    padding: 145px 0;
  }

  .SectionHeader:not(:only-child) {
    margin-bottom: 70px;
  }

  .SectionHeader__Description {
    margin-top: 24px;
  }

  .SectionHeader__ButtonWrapper {
    margin-top: 30px;
  }

  .SectionFooter {
    margin-top: 80px;
  }
}
.TableWrapper {
  overflow: auto;
  -webkit-overflow-scrolling: touch;
}

.Table {
  width: 100%;
  font-size: to-size(12px);
  border-collapse: separate;
  white-space: nowrap;

  th,
  td {
    padding: 18px 10px;
    border-bottom: 1px solid $border-color;
    text-align: left;
  }

  th:first-child,
  td:first-child,
  tfoot td:empty + td {
    padding-left: 0;
  }

  th:last-child,
  td:last-child {
    padding-right: 0;
  }

  th {
    font-family: $heading-font-family;
    font-weight: $heading-font-weight;
    font-style: $heading-font-style;
    text-transform: uppercase;
    letter-spacing: 0.2em;
  }

  thead th:first-child:empty,
  tbody th:first-child {
    position: -webkit-sticky;
    position: sticky;
    left: 0;
    min-width: 40px;
    max-width: 100px;
    z-index: 1;
    background: $background;
    white-space: normal;
  }

  tbody th:first-child {
    border-right: 1px solid $border-color;
  }

  tfoot td:empty {
    border-bottom: none;
  }
}

.Table--large td {
  padding-top: 25px;
  padding-bottom: 25px;
}

.Table--noBorder tbody tr:not(:last-child) td {
  border-bottom: none;
}

@include av-mq('phone') {
  .TableWrapper {
    margin-right: -24px;
    margin-left: -24px;
  }

  .TableWrapper > .Table {
    padding-right: 24px;
    padding-left: 24px;
  }
}

@include av-mq('desk') {
  .Table {
    white-space: normal;
  }

  .Table--large td {
    padding-top: 35px;
    padding-bottom: 35px;
  }
}


.TabList {
  white-space: nowrap;
  overflow: auto;
  -webkit-overflow-scrolling: touch;
}

.TabList__Item {
  position: relative;

  &::after {
    position: relative;
    display: block;
    content: '';
    bottom: 1px;
    left: 0;
    height: 1px;
    width: 0;
    background: $heading-color;
    -webkit-transition: width 0.25s ease-in-out;
    transition: width 0.25s ease-in-out;
  }
}

.TabList__Item + .TabList__Item {
  margin-left: 28px;
}

.TabList__Item.is-active::after {
  @if $uppercase-heading {
    width: calc(100% - 0.2em);
  } @else {
    width: 100%;
  }
}

.TabPanel {
  display: none;
}

.TabPanel[aria-hidden="false"] {
  display: block;
}

@include av-mq('tablet-and-up') {
  .TabList__Item + .TabList__Item {
    margin-left: 45px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Layout override
 * ----------------------------------------------------------------------------
 */

.template-customers {
  .OrderAddresses .Grid__Cell + .Grid__Cell {
    margin-top: 50px;
  }
}
@include av-mq('tablet') {
  .template-customers {
    .OrderAddresses .Grid__Cell + .Grid__Cell {
      margin-top: 0;
    }
  }
}

@include av-mq('desk') {
  .template-customers {
    .OrderAddresses .Grid__Cell + .Grid__Cell {
      margin-top: 65px;
    }
  }
}

/**
 * ----------------------------------------------------------------------------
 * Addresses
 * ----------------------------------------------------------------------------
 */

.AddressList {
  margin-bottom: -40px;

  .Grid__Cell {
    margin-bottom: 40px;
  }
}

.AccountAddress span {
  display: inline-block;
  margin-bottom: 12px;
}

@include av-mq('phone') {
  .Modal--address {
    height: 100%;
    width: 100%;
    max-width: none;
    max-height: none;
  }

  .Modal--address .Modal__Header {
    margin-top: 35px;
  }
}

@include av-mq('tablet') {
  .OrderAddresses {
    width: 100%;
    max-width: none;
  }
}

@include av-mq('tablet-and-up') {
  .AddressList {
    margin-bottom: -60px;

    .Grid__Cell {
      margin-bottom: 60px;
    }
  }
}

/**
 * ----------------------------------------------------------------------------
 * Account table
 * ----------------------------------------------------------------------------
 */

.AccountTable th {
  padding-top: 0;
  padding-bottom: 10px;
  font-size: to-size(11px);
}

.AccountTable tfoot {
  font-size: to-size(14px);
}

.AccountTable tfoot span + span {
  padding-left: 18px;
}

.AccountTable .CartItem__PriceList {
  margin-bottom: 0;
}

@include av-mq('phone') {
  .AccountTable .CartItem__ImageWrapper {
    width: 70px;
    min-width: 70px;
  }
}
/**
 * ----------------------------------------------------------------------------
 * Article inner
 * ----------------------------------------------------------------------------
 */

.Article__ImageWrapper {
  overflow: hidden;
  height: 215px;
}

.Article__Image {
  position: relative;
  height: 100%;
  width: 100%;
  background-size: cover;
  background-position: center;

  @supports (--css: variables) {
    height: calc(100% + var(--announcement-bar-height, 0px));
    top: calc(-1 * var(--announcement-bar-height, 0px));
  }
}

.Article__Wrapper {
  position: relative;
  max-width: 620px;
  margin: 0 auto 90px auto;
  padding: 24px 24px 0 24px;
  background: $background;
}

.Article__Header {
  margin-bottom: 35px;
}

.Article__Meta {
  margin-bottom: 18px;
}

.Article__MetaItem + .Article__MetaItem::before {
  position: relative;
  display: inline-block;
  content: '';
  height: 4px;
  width: 4px;
  border-radius: 100%;
  margin: 0 15px;
  font-size: to-size(10px);
  vertical-align: middle;
  background: currentColor;
}

.Article__Footer {
  margin-top: 45px;
}

.Article__ShareButtons {
  margin-top: 42px;
}

@include av-mq('tablet-and-up') {
  .Article__Wrapper {
    margin-bottom: 120px;
    padding: 40px 50px 0 50px;
  }

  .Article__ImageWrapper {
    height: 335px;
  }

  .Article__ImageWrapper + .Article__Wrapper {
    margin-top: -45px;
  }

  .Article__Header {
    margin-bottom: 45px;
  }

  .Article__Footer {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-pack: justify;
    -ms-flex-pack: justify;
    justify-content: space-between;
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
    margin-top: 65px;
  }

  .Article__ShareButtons {
    margin-top: 0;
  }
}

@include av-mq('lap-and-up') {
  .Article__Wrapper {
    max-width: 780px;
  }

  .Article__ImageWrapper {
    height: 450px;
  }

  .Article__ImageWrapper + .Article__Wrapper {
    margin-top: -70px;
  }
}

@include av-mq('desk') {
  .Article__ImageWrapper {
    height: 600px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Comments
 * ----------------------------------------------------------------------------
 */

.Article__CommentForm {
  margin-top: 40px;
}

.Article__Comments,
.Article__CommentFormWrapper {
  margin: 80px 0;
}

.Article__Comments .Pagination {
  margin-top: 40px;
}

.ArticleComment {
  margin-top: 35px;
}

.ArticleComment + .ArticleComment {
  padding-top: 35px;
  border-top: 1px solid $border-color;
}

.ArticleComment__Body {
  margin-bottom: 18px;
}

.ArticleComment__Date {
  margin-left: 15px;
}

@include av-mq('tablet-and-up') {
  .Article__Comments,
  .Article__CommentFormWrapper {
    margin: 105px 0;
  }

  .Article__Comments .Pagination {
    margin-top: 80px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Toolbar
 * ----------------------------------------------------------------------------
 */

.ArticleToolbar {
  position: fixed;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  top: 0;
  width: 100%;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  padding: 15px 30px 16px 30px;
  background: $secondary-elements-background;
  color: $secondary-elements-text-color;
  z-index: 2;
  -webkit-transform: translateY(-100%);
  transform: translateY(-100%);
  opacity: 0;
  will-change: transform, opacity;
  -webkit-transition: opacity 0.2s ease-in-out, -webkit-transform 0.2s ease-in-out;
  transition: opacity 0.2s ease-in-out, -webkit-transform 0.2s ease-in-out;
  transition: opacity 0.2s ease-in-out, transform 0.2s ease-in-out;
  transition: opacity 0.2s ease-in-out, transform 0.2s ease-in-out, -webkit-transform 0.2s ease-in-out;

  @supports (--css: variables) {
    top: calc(var(--use-sticky-header, 0) * var(--header-height));
  }
}

.ArticleToolbar.is-visible {
  -webkit-transform: translateY(0);
  transform: translateY(0);
  opacity: 1;
}

.ArticleToolbar .Link:hover {
  color: $secondary-elements-text-color;
}

.ArticleToolbar .Text--subdued {
  color: $secondary-elements-text-color-light;
}

.ArticleToolbar__ArticleTitle {
  position: relative;
  display: -webkit-inline-box;
  display: -ms-inline-flexbox;
  display: inline-flex;
  max-width: 285px;
  width: 285px;
  overflow: hidden;
  white-space: nowrap;
  text-overflow: clip;
  color: $secondary-elements-text-color;

  &::after {
    content: '';
    position: absolute;
    background: -webkit-gradient(linear, left top, right top, from(rgba($secondary-elements-background, 0.1)), to(rgba($secondary-elements-background, 1)));
    background: linear-gradient(to right, rgba($secondary-elements-background, 0.1), rgba($secondary-elements-background, 1));
    right: 0;
    top: 0;
    height: 100%;
    width: 35px;
  }
}

.ArticleToolbar__ShareList {
  display: inline-block;
}

.ArticleToolbar__ShareList .HorizontalList {
  display: inline-block;
  margin-left: 20px;
}

.ArticleToolbar__Nav {
  display: inline-block;
  margin-left: 50px;

  svg {
    color: $secondary-elements-text-color;
  }
}

.ArticleToolbar__NavItemSeparator {
  display: inline-block;
  position: relative;
  content: '';
  width: 1px;
  height: 12px;
  margin: 0 18px;
  background: rgba($secondary-elements-text-color-light, 0.6);
  vertical-align: middle;
}

.ArticleToolbar__NavItem svg {
  vertical-align: -1px;
}

.ArticleToolbar__NavItem--prev svg {
  margin-right: 6px;
}

.ArticleToolbar__NavItem--next svg {
  margin-left: 6px;
}

@include av-mq('lap-and-up') {
  .ArticleToolbar__ArticleTitle {
    max-width: 400px;
    width: 400px;
  }
}

@include av-mq('desk') {
  .ArticleToolbar {
    padding-left: 50px;
    padding-right: 50px;
  }

  .ArticleToolbar__ArticleTitle {
    max-width: 550px;
    width: 550px;
  }

  .ArticleToolbar__Nav {
    margin-left: 100px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Article navigation
 * ----------------------------------------------------------------------------
 */

.ArticleNav {
  padding: 75px 0;
  background: $secondary-elements-background;
  color: $secondary-elements-text-color;
}

.ArticleNav .Heading {
  color: inherit;
}

.ArticleNav__Item {
  display: block;
}

.ArticleNav__Image {
  height: 350px;
  background-size: cover;
  background-position: center;
}

@include av-mq('phone') {
  .ArticleNav .Grid__Cell + .Grid__Cell {
    margin-top: 50px;
  }
}

@include av-mq('tablet-and-up') {
  .ArticleNav {
    padding: 140px 0;
  }
}
/**
 * ----------------------------------------------------------------------------
 * Article item
 * ----------------------------------------------------------------------------
 */

.ArticleListWrapper {
  max-width: 1260px;
  margin: 0 auto 60px auto;
}

.ArticleList {
  margin-bottom: -60px;
}

.ArticleList .Grid__Cell {
  margin-bottom: 60px;
}

@if $show-element-staggering {
  .js .ArticleItem {
    visibility: hidden;
  }
}

.ArticleItem__ImageWrapper {
  display: block;
  margin-bottom: 22px;
  background-size: cover;
  overflow: hidden;
}

.ArticleItem__Image {
  display: block;
  -o-object-fit: cover;
  object-fit: cover;
  -o-object-position: center;
  object-position: center;
  font-family: 'object-fit: cover; object-position: center;';
  -webkit-transform: scale(1);
  transform: scale(1);
  -webkit-transition: opacity 0.3s ease, -webkit-transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  transition: opacity 0.3s ease, -webkit-transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  transition: opacity 0.3s ease, transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  transition: opacity 0.3s ease, transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94), -webkit-transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}

.ArticleList .ImageHero__ImageWrapper {
  -webkit-transition: -webkit-transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  transition: -webkit-transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  transition: transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  transition: transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94), -webkit-transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}

@media (-moz-touch-enabled: 0), (hover: hover) {
  .ArticleItem:hover .ArticleItem__Image,
  .ArticleList .ImageHero:hover .ImageHero__ImageWrapper {
    -webkit-transform: scale(1.2);
    transform: scale(1.2);
  }
}

.ArticleItem__Content {
  margin: 0 8px;
}

.ArticleItem__Category {
  display: block;
  margin-bottom: 16px;
}

.ArticleItem__Excerpt {
  margin-bottom: 20px;
}

@include av-mq('tablet-and-up') {
  .ArticleList--withFeatured .Grid__Cell:first-child {
    margin-bottom: 40px;
  }

  .ArticleItem__Content {
    margin: 0 18px;
  }
}

@include av-mq('lap-and-up') {
  .ArticleListWrapper {
    margin-bottom: 100px;
  }

  .ArticleList {
    margin-bottom: -100px;
  }

  .ArticleList .Grid__Cell {
    margin-bottom: 100px;
  }

  .ArticleList--withFeatured .Grid__Cell:first-child {
    margin-bottom: 60px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Blog
 * ----------------------------------------------------------------------------
 */

.Blog__RssLink {
  margin-left: 14px;
  vertical-align: baseline;

  svg {
    width: 10px;
    height: 10px;
  }
}

.Blog__TagList {
  padding-top: 8px;
}

.Blog__TagList .Link.is-active::after {
  display: block;
  content: '';
  width: calc(100% - 0.15em);
  height: 1px;
  background: currentColor;
}

@include av-mq('phone') {
  .Blog__TagList .HorizontalList__Item {
    margin: 5px 10px;
  }
}

@include av-mq('tablet-and-up') {
  .ArticleList + .Pagination {
    margin-top: 80px;
  }
}

@include av-mq('desk') {
  #shopify-section-blog-template + #shopify-section-shop-now {
    margin-top: 150px;
  }
}
/**
 * ----------------------------------------------------------------------------
 * General
 * ----------------------------------------------------------------------------
 */

@-webkit-keyframes cartEmptyOpening {
  from {
    -webkit-transform: translate(-50%, calc(-50% + 35px));
    transform: translate(-50%, calc(-50% + 35px));
    opacity: 0;
  }

  to {
    -webkit-transform: translate(-50%, -50%);
    transform: translate(-50%, -50%);
    opacity: 1;
  }
}

@keyframes cartEmptyOpening {
  from {
    -webkit-transform: translate(-50%, calc(-50% + 35px));
    transform: translate(-50%, calc(-50% + 35px));
    opacity: 0;
  }

  to {
    -webkit-transform: translate(-50%, -50%);
    transform: translate(-50%, -50%);
    opacity: 1;
  }
}

.Cart__ShippingNotice {
  position: -webkit-sticky;
  position: sticky;
  top: 0;
  margin-bottom: 0;
  padding-top: 9px;
  padding-bottom: 9px;
  font-size: to-size(11px);
  border-bottom: 1px solid $border-color;
  line-height: normal;
  z-index: 1;
  background: $background;
}

.Cart__Empty {
  position: absolute;
  width: 100%;
  top: 50%;
  left: 50%;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  text-align: center;
  -webkit-animation: cartEmptyOpening 0.8s cubic-bezier(0.215, 0.61, 0.355, 1);
  animation: cartEmptyOpening 0.8s cubic-bezier(0.215, 0.61, 0.355, 1);
}

@include av-mq('tablet-and-up') {
  .Cart__ShippingNotice {
    font-size: to-size(13px);
  }
}

/**
 * ----------------------------------------------------------------------------
 * Items
 * ----------------------------------------------------------------------------
 */

.CartItemWrapper {
  overflow: hidden;
}

.CartItem {
  display: table;
  table-layout: fixed;
  margin: 30px 0;
  width: 100%;
}

.CartItem__ImageWrapper,
.CartItem__Info {
  display: table-cell;
  vertical-align: middle;
}

.CartItem__ImageWrapper {
  width: 90px;
  min-width: 90px;
  text-align: center;
}

.CartItem__Info {
  padding-left: 25px;
}

.CartItem__Title {
  width: 100%;
  font-size: to-size(11px);
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.CartItem__Title,
.CartItem__Variant,
.CartItem__PropertyList {
  margin-bottom: 0.45em;
}

.CartItem__Meta {
  font-size: to-size(9px);
}

.CartItem__PropertyList {
  list-style: none;
  font-style: italic;
}

.CartItem__Actions {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  -ms-flex-wrap: wrap;
  flex-wrap: wrap;
}

.CartItem__PriceList {
  margin-bottom: 16px;
}

.CartItem__Remove {
  margin: 8px 0;
  font-size: to-size(8px);

  &::before {
    background: lighten($text-color-light, 15%);
  }
}

@include av-mq('tablet-and-up') {
  .CartItem__ImageWrapper {
    width: 120px;
  }

  .CartItem__Title {
    font-size: to-size(12px);
  }

  .CartItem__Meta {
    font-size: to-size(11px);
  }

  .CartItem__Remove {
    font-size: to-size(9px);
  }

  .CartItem__PriceList {
    margin-bottom: 20px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Bottom
 * ----------------------------------------------------------------------------
 */

.Cart .Drawer__Footer,
.Cart__OffscreenNoteContainer {
  padding: 14px 24px 24px 24px;
}

.Cart__Taxes {
  display: block;
}

.Cart__Checkout {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  margin-top: 18px;
}

.Cart__OffscreenNoteContainer {
  position: absolute;
  width: 100%;
  bottom: 0;
  left: 0;
  z-index: 1;
  background: $background;
  border-top: 1px solid $border-color;
  -webkit-transform: translateY(100%);
  transform: translateY(100%);
  -webkit-transition: -webkit-transform 0.25s ease-in-out;
  transition: -webkit-transform 0.25s ease-in-out;
  transition: transform 0.25s ease-in-out;
  transition: transform 0.25s ease-in-out, -webkit-transform 0.25s ease-in-out;
}

.Cart__OffscreenNoteContainer[aria-hidden="false"] {
  -webkit-transform: translateY(0);
  transform: translateY(0);
  -webkit-box-shadow: 1px 0 6px rgba(#363636, 0.2);
  box-shadow: 1px 0 6px rgba(#363636, 0.2);
}

.Cart__Note {
  margin-top: 10px;
}

.has-note-open[aria-hidden="false"] .Drawer__Header,
.has-note-open[aria-hidden="false"] .Drawer__Main {
  opacity: 0.4;
  pointer-events: none;
  -webkit-transition: opacity 0.5s ease;
  transition: opacity 0.5s ease;
}

@include av-mq('tablet-and-up') {
  .Cart .Drawer__Footer,
  .Cart__OffscreenNoteContainer {
    padding: 20px 30px 30px 30px;
  }

  .Cart__NoteButton + .Cart__Taxes {
    margin-top: 4px;
  }

  .Cart__Taxes {
    margin-bottom: 8px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Adjustments for dedicated cart page
 * ----------------------------------------------------------------------------
 */

.Cart--expanded {
  .Cart__Footer {
    padding-top: 25px;
    border-top: 1px solid $border-color;
  }

  .Cart__Recap {
    text-align: right;
  }

  .Cart__Recap,
  .Cart__Recap .Cart__Checkout {
    margin-top: 16px;
  }
}

@include av-mq('phone') {
  .CartItem__Info ~ .CartItem__Actions,
  .CartItem__Info ~ .CartItem__LinePrice {
    display: none;
  }
}

@include av-mq('tablet-and-up') {
  .Cart--expanded {
    .Cart__ItemList {
      display: table;
      table-layout: auto;
      border-spacing: 0 30px;
      width: 100%;
    }

    .Cart__Head {
      display: table-header-group;
    }

    .Cart__HeadItem {
      display: table-cell;
      padding-bottom: 10px;
      border-bottom: 1px solid $border-color;
    }

    .CartItem {
      display: table-row;
    }

    .CartItem__Info {
      max-width: 300px;
      width: 300px;
    }

    .CartItem__Info > .CartItem__Actions {
      display: none;
    }

    .CartItem__Info ~ .CartItem__Actions,
    .CartItem__Info ~ .CartItem__LinePrice {
      display: table-cell;
      vertical-align: middle;
    }

    .CartItem__QuantitySelector {
      margin-bottom: 6px;
    }

    .Cart__Footer {
      display: table;
      width: 100%;
      table-layout: fixed;
    }

    .Cart__Recap,
    .Cart__NoteContainer {
      display: table-cell;
    }

    .Cart__NoteContainer {
      width: 340px;
    }

    .Cart__Checkout {
      width: auto;
    }
  }
}

@include av-mq('desk') {
  .Cart--expanded {
    .CartItem__Info {
      max-width: 425px;
      width: 425px;
    }
  }
}

/**
 * ----------------------------------------------------------------------------
 * Shipping estimator
 * ----------------------------------------------------------------------------
 */

.ShippingEstimator__Results {
  height: 0;
  overflow: hidden;
  -webkit-transition: height 0.25s ease-in-out;
  transition: height 0.25s ease-in-out;
}

.ShippingEstimator__Error,
.ShippingEstimator__ResultsInner {
  margin-top: 32px;
}

.ShippingEstimator__Results p {
  margin-bottom: 0.5em;
}

@include av-mq('phone') {
  .ShippingEstimator__Submit {
    width: 100%;
  }

  .ShippingEstimator__Country,
  .ShippingEstimator__Province,
  .ShippingEstimator__Zip {
    margin-bottom: 20px;
  }
}

@include av-mq('tablet-and-up') {
  .ShippingEstimator__Form {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
  }

  .ShippingEstimator__Form > *:not(:first-child) {
    margin-left: 20px;
  }

  .ShippingEstimator__Country,
  .ShippingEstimator__Province {
    margin-bottom: 0;
  }

  .ShippingEstimator__Zip {
    margin-bottom: 0;
    max-width: 130px;
  }
}
/**
 * ----------------------------------------------------------------------------
 * Collection item (for list of collections)
 * ----------------------------------------------------------------------------
 */

.CollectionList::after {
  content: 'flickity';
  display: none;
}

.CollectionItem__Wrapper {
  position: relative;
  height: 500px;
  background-size: cover;
  background-position: center;
  overflow: hidden;
}

.CollectionItem__Wrapper--small {
  height: 450px;
}

.CollectionItem__Wrapper--large {
  height: 550px;
}

.CollectionItem__ImageWrapper {
  background-size: cover;
  background-position: center;
  height: 100%;
  width: 100%;
  -webkit-transform: scale(1);
  transform: scale(1);
  -webkit-transition: -webkit-transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  transition: -webkit-transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  transition: transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  transition: transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94), -webkit-transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}

.CollectionItem__Image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-size: cover;
}

.CollectionItem__Content {
  position: absolute;
  padding: 0 24px;
  margin-bottom: 0 !important;
  top: 50%;
  left: 50%;
  width: 100%;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  text-align: center;
}

@media (-moz-touch-enabled: 0), (hover: hover) {
  .CollectionItem:hover .CollectionItem__ImageWrapper {
    -webkit-transform: scale(1.2);
    transform: scale(1.2);
  }
}

@include av-mq('phone') {
  .CollectionList--grid {
    margin: -12px 12px 12px 12px;
  }

  .CollectionList--grid .CollectionItem {
    padding: 12px;
  }
}

@include av-mq('tablet-and-up') {
  .CollectionList {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -ms-flex-wrap: wrap;
    flex-wrap: wrap;
    margin-bottom: 0;

    &::after {
      content: ''; /* disable Flickity */
    }
  }

  .CollectionList--spaced {
    margin: 15px;
  }

  .CollectionList--spaced .CollectionItem {
    padding: 15px;
  }

  .CollectionList--grid.CollectionList--spaced {
    margin-top: -15px;
  }

  .CollectionItem {
    display: block !important;
    -webkit-box-flex: 0;
    -ms-flex: 0 1 0px;
    flex: 0 1 0;
    min-width: 50%;
  }

  .CollectionItem--expand {
    -webkit-box-flex: 1;
    -ms-flex-positive: 1;
    flex-grow: 1;
  }

  .CollectionItem__Content {
    padding: 0 40px;
    text-align: left;
  }

  .CollectionItem__Content--bottomCenter,
  .CollectionItem__Content--middleCenter {
    text-align: center;
  }

  .CollectionItem__Content--bottomRight,
  .CollectionItem__Content--middleRight {
    text-align: right;
  }

  .CollectionItem__Content--bottomLeft,
  .CollectionItem__Content--bottomRight,
  .CollectionItem__Content--bottomCenter {
    bottom: 40px;
    top: auto;
    left: 0;
    -webkit-transform: none;
    transform: none;
  }
}

@include av-mq('desk') {
  .CollectionItem {
    min-width: 33.33333%;
  }

  .CollectionItem__Wrapper {
    height: 600px;
  }

  .CollectionItem__Wrapper--small {
    height: 500px;
  }

  .CollectionItem__Wrapper--large {
    height: 700px;
  }

  .CollectionItem__Content {
    padding: 0 50px;
  }

  .CollectionItem__Content--bottomLeft,
  .CollectionItem__Content--bottomRight,
  .CollectionItem__Content--bottomCenter {
    bottom: 50px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Collection toolbar
 * ----------------------------------------------------------------------------
 */

.CollectionToolbar {
  position: -webkit-sticky;
  position: sticky;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  width: 100%;
  background: $background;
  -webkit-box-shadow: 1px 1px $border-color, -1px -1px $border-color;
  box-shadow: 1px 1px $border-color, -1px -1px $border-color;
  z-index: 2;
}

.CollectionToolbar--top {
  top: $header-base-height;

  @supports (--css: variables) {
    top: calc(var(--header-height) * var(--use-sticky-header, 0));
  }
}

.supports-sticky .CollectionToolbar--bottom {
  bottom: 0; /* as of today the best polyfill I've found does not support polyfilling sticky on bottom. As a consequence on those old
                browsers, the stickiness is always at the top */
}

.CollectionToolbar__Group {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-flex: 1;
  -ms-flex: 1 0 auto;
  flex: 1 0 auto;
}

.CollectionToolbar__Item {
  -webkit-box-flex: 1;
  -ms-flex: 1 0 auto;
  flex: 1 0 auto;
  padding: 13px 0;
  border-left: 1px solid $border-color;
  text-align: center;
  vertical-align: middle;
  cursor: pointer;
  -webkit-transition: background 0.2s ease-in-out;
  transition: background 0.2s ease-in-out;
}

.CollectionToolbar__Item--sort .Icon--select-arrow {
  height: 6px;
  margin-left: 2px;
  pointer-events: none;
}

.CollectionToolbar__Item--layout {
  -webkit-box-flex: 0;
  -ms-flex: none;
  flex: none;
  width: 95px;
  line-height: 1;
  cursor: initial;
}

.CollectionToolbar__LayoutType {
  margin: 0 6px;
  opacity: 0.2;
  -webkit-transition: opacity 0.25s ease-in-out;
  transition: opacity 0.25s ease-in-out;

  svg {
    width: 18px;
    height: 18px;
  }
}

.CollectionToolbar__LayoutType.is-active {
  opacity: 1;
}

@include av-mq('phone') {
  .CollectionToolbar__Item:first-child {
    border-left: none;
  }
}

@include av-mq('tablet-and-up') {
  .CollectionToolbar--reverse,
  .CollectionToolbar__Group {
    -webkit-box-orient: horizontal;
    -webkit-box-direction: reverse;
    -ms-flex-direction: row-reverse;
    flex-direction: row-reverse;
  }

  .CollectionToolbar__Group {
    -webkit-box-flex: 0;
    -ms-flex: none;
    flex: none;
  }

  .CollectionToolbar__Item {
    padding: 18px 0;
  }

  .CollectionToolbar__Group .CollectionToolbar__Item {
    padding-left: 45px;
    padding-right: 45px;
  }

  .CollectionToolbar__Item--layout {
    border-left: none;
    width: 115px;
    border-right: 1px solid $border-color;
    white-space: nowrap;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Collection filters
 * ----------------------------------------------------------------------------
 */

.CollectionFilters .Collapsible:first-child {
  border-top: none;
}

@include av-mq('tablet-and-up') {
  .CollectionFilters .Drawer__Main {
    padding-top: 35px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Product item
 * ----------------------------------------------------------------------------
 */

.ProductItem {
  text-align: center;
  white-space: normal;
}

@if $show-element-staggering {
  .js .ProductList--grid .ProductItem {
    visibility: hidden;
  }
}

.ProductItem__Wrapper {
  position: relative;
}

.ProductItem__ImageWrapper {
  display: block;
}

.ProductItem__Image--alternate {
  position: absolute;
  top: 0;
  left: 0;
  opacity: 0 !important;
  -o-object-fit: cover;
  object-fit: cover;
  -o-object-position: center;
  object-position: center;
}

.ProductItem__LabelList {
  position: absolute;
  left: 10px;
  top: 6px;
  text-align: left;
}

.ProductItem__Label {
  display: block;
  font-size: to-size(9px);
  margin: 4px 0;
  padding: 2px 6px;
  background: $background;
}

.ProductItem__Info {
  margin-top: 20px;

  @if $uppercase-heading {
    font-size: to-size(11px);
  } @else {
    font-size: to-size(12px);
  }
}

.ProductItem__Info--left {
  text-align: left;
}

.ProductItem__Info--right {
  text-align: right;
}

.ProductItem__Title {
  display: block;
  margin-bottom: 4px;
}

.ProductItem__ColorSwatchList {
  margin-top: 15px;
}

.ProductItem__ColorSwatchItem {
  display: inline-block;
  margin: 0 5px;
}

.ProductItem__ColorSwatchList + .ProductItem__PriceList {
  margin-top: 12px;
}

@media (-moz-touch-enabled: 0), (hover: hover) {
  @if $product-show-price-on-hover {
    .ProductItem__PriceList--showOnHover {
      opacity: 0;
      -webkit-transform: translateY(10px);
      transform: translateY(10px);
      -webkit-transition: all 0.35s ease-in-out;
      transition: all 0.35s ease-in-out;
    }

    .ProductItem:hover .ProductItem__PriceList--showOnHover {
      opacity: 1;
      -webkit-transform: translateY(0);
      transform: translateY(0);
    }
  }

  .ProductItem__ImageWrapper--withAlternateImage:hover .ProductItem__Image {
    opacity: 0 !important;
  }

  .ProductItem__ImageWrapper--withAlternateImage:hover .ProductItem__Image--alternate {
    opacity: 1 !important;
  }
}

@media (-moz-touch-enabled: 1), (hover: none) {
  .ProductItem__Image--alternate {
    display: none; /* This prevents the image to be lazy-loaded */
  }
}

@include av-mq('tablet-and-up') {
  .ProductItem__Label {
    font-size: to-size(11px);
  }

  .ProductItem__Info {
    @if $uppercase-heading {
      font-size: to-size(12px);
    } @else {
      font-size: to-size(13px);
    }
  }
}

@include av-mq('lap-and-up') {
  .ProductItem--horizontal {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-pack: justify;
    -ms-flex-pack: justify;
    justify-content: space-between;
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;

    .ProductItem__Wrapper {
      display: -webkit-box;
      display: -ms-flexbox;
      display: flex;
      -webkit-box-align: center;
      -ms-flex-align: center;
      align-items: center;
    }

    .ProductItem__ImageWrapper {
      min-width: 100px;
    }

    .ProductItem__Info {
      margin: 0 30px 0 40px;
      text-align: left;
    }

    .ProductItem__ViewButton {
      -ms-flex-negative: 0;
      flex-shrink: 0;
    }
  }
}

/**
 * ----------------------------------------------------------------------------
 * Product grid
 * ----------------------------------------------------------------------------
 */

.CollectionInner {
  margin-top: 24px;
}

.ProductList--grid {
  padding: 0 12px;
}

@include av-mq('phone') {
  .ProductList--grid {
    margin-left: -10px;
  }

  .ProductList--removeMargin {
    margin-bottom: -35px !important;
  }

  .ProductList--grid > .Grid__Cell {
    padding-left: 10px;
    margin-bottom: 35px;
  }
}

@include av-mq('tablet-and-up') {
  .CollectionInner {
    margin-top: 50px;
  }

  .ProductList--grid {
    padding: 0 24px;
    margin-left: -24px;
  }

  .ProductList--removeMargin {
    margin-bottom: -50px !important;
  }

  .ProductList--grid > .Grid__Cell {
    padding-left: 24px;
    margin-bottom: 50px;
  }
}

@include av-mq('lap-and-up') {
  .CollectionInner {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
  }

  .CollectionInner__Sidebar {
    position: -webkit-sticky;
    position: sticky;
    top: 200px;
    -webkit-box-flex: 0;
    -ms-flex: none;
    flex: none;
    -ms-flex-item-align: start;
    align-self: flex-start;
    width: 200px;
    margin: 0 16px 0 24px;
    padding-bottom: 50px;

    @supports (--css: variables) {
      top: calc(var(--header-height) + 50px);
    }
  }

  @supports (--css: variables) {
    .CollectionInner__Sidebar--withTopToolbar {
      top: calc(var(--header-height) * var(--use-sticky-header, 0) + 105px);
    }
  }

  .CollectionInner__Products {
    -webkit-box-flex: 1;
    -ms-flex: 1 0 0px;
    flex: 1 0 0;
  }

  .CollectionInner__Sidebar .Collapsible {
    padding: 0;
  }
}

$horizontal-spacing-four-products-per-row: 0px;
$vertical-spacing-four-products-per-row  : 0px;

$horizontal-spacing-two-products-per-row: 0px;
$vertical-spacing-two-products-per-row  : 0px;

@if ($product-list-horizontal-spacing == 'extra_small') {
  $horizontal-spacing-four-products-per-row: 20px;
  $horizontal-spacing-two-products-per-row : 20px;
} @else if ($product-list-horizontal-spacing == 'small') {
  $horizontal-spacing-four-products-per-row: 40px;
  $horizontal-spacing-two-products-per-row : 40px;
} @else if ($product-list-horizontal-spacing == 'medium') {
  $horizontal-spacing-four-products-per-row: 60px;
  $horizontal-spacing-two-products-per-row : 60px;
} @else if ($product-list-horizontal-spacing == 'large') {
  $horizontal-spacing-four-products-per-row: 80px;
  $horizontal-spacing-two-products-per-row : 80px;
} @else if ($product-list-horizontal-spacing == 'extra_large') {
  $horizontal-spacing-four-products-per-row: 100px;
  $horizontal-spacing-two-products-per-row : 100px;
}

@if ($product-list-vertical-spacing == 'extra_small') {
  $vertical-spacing-four-products-per-row: 40px;
  $vertical-spacing-two-products-per-row : 50px;
} @else if ($product-list-vertical-spacing == 'small') {
  $vertical-spacing-four-products-per-row: 60px;
  $vertical-spacing-two-products-per-row : 75px;
} @else if ($product-list-vertical-spacing == 'medium') {
  $vertical-spacing-four-products-per-row: 80px;
  $vertical-spacing-two-products-per-row : 100px;
} @else if ($product-list-vertical-spacing == 'large') {
  $vertical-spacing-four-products-per-row: 100px;
  $vertical-spacing-two-products-per-row : 125px;
} @else if ($product-list-vertical-spacing == 'extra_large') {
  $vertical-spacing-four-products-per-row: 120px;
  $vertical-spacing-two-products-per-row : 150px;
}

@include av-mq('desk') {
  .CollectionInner__Sidebar {
    margin-right: 10px;
    margin-left: 50px;
  }

  .CollectionInner .Pagination {
    margin-bottom: 80px;
  }

  .ProductList--grid {
    padding: 0 50px;
  }

  .ProductList--grid[data-desktop-count="2"] {
    margin-left: -$horizontal-spacing-two-products-per-row;

    & > .Grid__Cell {
      padding-left: $horizontal-spacing-two-products-per-row;
      margin-bottom: $vertical-spacing-two-products-per-row;
    }
  }

  .ProductList--removeMargin[data-desktop-count="2"] {
    margin-bottom: -$vertical-spacing-two-products-per-row !important;
  }

  .ProductList--grid[data-desktop-count="4"],
  .ProductList--grid[data-desktop-count="3"] {
    margin-left: -$horizontal-spacing-four-products-per-row;

    & > .Grid__Cell {
      padding-left: $horizontal-spacing-four-products-per-row;
      margin-bottom: $vertical-spacing-four-products-per-row;
    }
  }

  .ProductList--removeMargin[data-desktop-count="4"],
  .ProductList--removeMargin[data-desktop-count="3"] {
    margin-bottom: -$vertical-spacing-four-products-per-row !important;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Product carousel
 * ----------------------------------------------------------------------------
 */

.ProductList--carousel .Carousel__Cell {
  width: 62%;
  padding: 0 12px;
  vertical-align: top;
}

@include av-mq('phone') {
  .template-search .ProductList--grid,
  .template-collection .ProductList--grid {
    margin-bottom: 20px; /* hack, would require some better code */
  }
}

@include av-mq('pocket') {
  /* On phone and tablet we do not use the carousel but instead use a free scroll, which offers better performance */

  .ProductListWrapper {
    overflow: hidden;
  }

  .ProductList--carousel {
    white-space: nowrap;
    overflow-x: auto;
    overflow-y: hidden;
    -webkit-overflow-scrolling: touch;
    padding-bottom: 30px; /* This is a trick to hide the scrollbar on iOS */
    margin-bottom: -30px;
  }

  .ProductList--carousel .Carousel__Cell {
    display: inline-block !important;

    &:first-child {
      margin-left: 19%; /* This is (100% - 62%) / 2, where 62% is the width of a single cell */
    }

    &:last-child {
      margin-right: 19%; /* This is (100% - 62%) / 2, where 62% is the width of a single cell */
    }
  }
}

@include av-mq('tablet') {
  .ProductList--carousel .Carousel__Cell {
    width: 48%;
    padding: 0 15px;

    &:first-child {
      margin-left: 26%; /* This is (100% - 48%) / 2, where 48% is the width of a single cell */
    }

    &:last-child {
      margin-right: 26%; /* This is (100% - 48%) / 2, where 48% is the width of a single cell */
    }
  }
}

@include av-mq('lap-and-up') {
  .ProductList--carousel {
    margin: 0 90px;

    &::after {
      content: 'flickity';
      display: none;
    }

    .Carousel__Cell {
      width: 33.3333%;
      left: 0;
      padding: 0 ($horizontal-spacing-four-products-per-row / 2);
      margin-left: 0;
    }

    .flickity-prev-next-button {
      top: calc(50% - 45px);
      width: 45px;
      height: 45px;
      stroke-width: 1px;
    }

    .flickity-prev-next-button.next {
      right: -50px;
    }

    .flickity-prev-next-button.previous {
      left: -50px;
    }
  }
}

@include av-mq('desk') {
  .ProductList--carousel .Carousel__Cell {
    width: 25%;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Product shop now
 * ----------------------------------------------------------------------------
 */

.ProductList--shopNow {
  position: static;
}

.ProductList--shopNow .Carousel__Cell {
  padding: 0 60px;
}

@include av-mq('phone') {
  .ShopNowGrid .FeaturedQuote {
    margin: 50px -24px -90px -24px;
  }
}

@include av-mq('tablet') {
  .ShopNowGrid .FeaturedQuote {
    margin: 60px -50px -90px -50px;
  }
}

@include av-mq('tablet-and-up') {
  .ProductList--shopNow {
    padding: 0 50px;
    overflow: hidden;
  }

  .ProductList--shopNow .flickity-viewport {
    overflow: visible;
  }

  .ProductList--shopNow .Carousel__Cell {
    width: 50%;
    padding: 0 50px;
  }
}

@include av-mq('lap-and-up') {
  .ProductList--shopNow[data-desktop-count="3"] .Carousel__Cell {
    width: 33.333333%;
  }

  .ShopNowGrid {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
  }

  .ShopNowGrid .FeaturedQuote {
    height: 100%;
  }
}
.Faq__Section {
  margin-bottom: 20px;
}

.Faq__Section ~ .Faq__Section {
  margin-top: 34px;
}

.Faq__Item {
  position: relative;
  margin: 14px 0;
}

.Faq__Icon {
  position: absolute;
  top: 0;
  left: 0;
  color: $text-color-light;
  -webkit-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;

  svg {
    width: 8px;
    height: 10px;
    vertical-align: baseline;
  }
}

.Faq__Item[aria-expanded="true"] .Faq__Icon {
  -webkit-transform: rotateZ(90deg);
  transform: rotateZ(90deg);
  color: $heading-color;
}

.Faq__ItemWrapper {
  padding-left: 26px;
}

.Faq__Question {
  display: block;
  width: 100%;
  margin-bottom: 0;
  text-align: left;
}

.Faq__AnswerWrapper {
  height: 0;
  overflow: hidden;
  visibility: hidden;
  -webkit-transition: height 0.25s ease-in-out, visibility 0s ease-in-out 0.25s;
  transition: height 0.25s ease-in-out, visibility 0s ease-in-out 0.25s;
}

.Faq__Item[aria-expanded="true"] .Faq__AnswerWrapper {
  visibility: visible;
  -webkit-transition: height 0.25s ease-in-out;
  transition: height 0.25s ease-in-out;
}

.Faq__Answer {
  padding: 16px 0 22px 0;
}

.Faq__Item--lastOfSection .Faq__Answer {
  padding-bottom: 0;
}

.FaqSummary {
  list-style: none;
  margin: 0;
  padding: 0;
}

.FaqSummary__Item {
  margin-bottom: 12px;
}

.FaqSummary__Item.is-active::after {
  width: 100%;
}

.FaqSummary__Link {
  display: block;
}

.FaqSummary__LinkLabel {
  position: relative;
  display: inline-block;

  &::after {
    position: absolute;
    content: '';
    left: 0;
    bottom: 0;
    width: 100%;
    height: 1px;
    -webkit-transform: scale(0, 1);
    transform: scale(0, 1);
    -webkit-transform-origin: left center;
    transform-origin: left center;
    background: currentColor;
    -webkit-transition: -webkit-transform 0.2s linear;
    transition: -webkit-transform 0.2s linear;
    transition: transform 0.2s linear;
    transition: transform 0.2s linear, -webkit-transform 0.2s linear;
  }
}

.FaqSummary__Item.is-active .FaqSummary__LinkLabel::after {
  -webkit-transform: scale(1, 1);
  transform: scale(1, 1);
}

@include av-mq('tablet-and-up') {
  .Faq__Section {
    margin-bottom: 34px;
  }

  .Faq__Section ~ .Faq__Section {
    margin-top: 60px;
  }
}
/**
 * As of today this section is displayed on the home page only
 */

.FeatureText {
  text-align: center;
}

.FeatureText__ContentWrapper {
  padding-left: 24px;
  padding-right: 24px;
}

.FeatureText__ImageWrapper {
  overflow: hidden;
}

.FeatureText--withImage .FeatureText__ContentWrapper {
  padding-top: 50px;
  padding-bottom: 20px;
}

.FeatureText .SectionHeader__Description {
  margin-top: 25px;
  margin-bottom: 20px;
}

@include av-mq('phone') {
  .FeatureText--imageLeft {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-orient: vertical;
    -webkit-box-direction: reverse;
    -ms-flex-direction: column-reverse;
    flex-direction: column-reverse;
  }
}

@include av-mq('tablet-and-up') {
  .FeatureText__Content {
    max-width: 430px;
    margin: 0 auto;
  }

  .FeatureText--withImage {
    display: table;
    width: 100%;
    text-align: left;
    table-layout: fixed;

    .FeatureText__ContentWrapper,
    .FeatureText__ImageWrapper {
      display: table-cell;
      width: 50%;
      vertical-align: middle;
    }

    .FeatureText__ContentWrapper {
      padding: 50px;
    }
  }

  .FeatureText--imageRight {
    .FeatureText__ContentWrapper {
      padding-right: 40px;
    }

    .FeatureText__Content,
    .AspectRatio {
      margin-right: 0;
    }

    .AspectRatio {
      text-align: right;
    }
  }

  .FeatureText--imageLeft {
    .FeatureText__ContentWrapper {
      padding-left: 40px;
    }

    .FeatureText__Content,
    .AspectRatio {
      margin-left: 0;
    }

    .AspectRatio {
      text-align: left;
    }
  }
}

@include av-mq('desk') {
  .FeatureText--imageRight .FeatureText__ContentWrapper {
    padding-right: 100px;
  }

  .FeatureText--imageLeft .FeatureText__ContentWrapper {
    padding-left: 100px;
  }
}
.shopify-section--bordered + .shopify-section--footer {
  border-top: 1px solid $footer-border-color;
}

.Footer {
  padding: 34px 0;
  background: $footer-background;
  color: $footer-text-color;

  @if $footer-background == $background {
    border-top: 1px solid $border-color;
  }
}

.Footer--withMargin {
  margin-top: 60px;
}

.Footer .Heading,
.Footer .Link--primary:hover {
  color: $footer-heading-color;
}

.Footer .Link--secondary:hover {
  color: $footer-text-color;
}

.Footer__Block {
  margin-top: 48px;

  &:first-child {
    margin-top: 0;
  }
}

.Footer__Title {
  margin-bottom: 20px;
}

.Footer__Social {
  margin-top: 5px;
}

.Footer__Content + .Footer__Newsletter {
  margin-top: 18px;
}

.Footer__Aside {
  text-align: center;
}

.Footer__Inner + .Footer__Aside {
  margin-top: 65px;
}

.Footer__ThemeAuthor {
  margin-top: 4px;
}

.Footer__PaymentList {
  margin: 54px -24px 0 -24px;
  padding-top: 28px;
  border-top: 1px solid $footer-border-color;
}

.Footer__PaymentList svg {
  opacity: 0.8;
  width: 38px;
  height: 24px;
}

@include av-mq('tablet-and-up') {
  .Footer {
    padding: 75px 0 42px 0;
  }

  .Footer--withMargin {
    margin-top: 80px;
  }

  .Footer__Inner {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -ms-flex-wrap: wrap;
    flex-wrap: wrap;
    -webkit-box-pack: justify;
    -ms-flex-pack: justify;
    justify-content: space-between;
    margin-left: -40px;
    margin-right: -40px;
  }

  .Footer__Block {
    -webkit-box-flex: 1;
    -ms-flex: 1 1 50%;
    flex: 1 1 50%;
    margin-top: 0;
    margin-bottom: 50px;
    padding-left: 40px;
    padding-right: 40px;
  }

  .Footer__Social {
    margin-top: 14px;
  }

  .Footer__Aside {
    text-align: left;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-pack: justify;
    -ms-flex-pack: justify;
    justify-content: space-between;
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
  }

  .Footer__Inner + .Footer__Aside {
    margin-top: 80px;
  }

  .Footer__StoreName {
    font-size: to-size(11px);
  }

  .Footer__PaymentList {
    padding: 0;
    margin: 0 -8px;
    border: none;
  }
}

@include av-mq('desk') {
  .Footer--withMargin {
    margin-top: 120px;
  }

  .Footer__Inner {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -ms-flex-wrap: wrap;
    flex-wrap: wrap;
    -webkit-box-pack: justify;
    -ms-flex-pack: justify;
    justify-content: space-between;
  }

  .Footer--center .Footer__Inner {
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    justify-content: center;
  }

  .Footer__Block {
    -webkit-box-flex: 0;
    -ms-flex: 0 1 auto;
    flex: 0 1 auto;
  }

  .Footer__Block--text,
  .Footer__Block--newsletter{
    -ms-flex-preferred-size: 240px;
    flex-basis: 240px;
  }
}

@include av-mq('desk') {
  .Footer__Block--text {
    -ms-flex-preferred-size: 460px;
    flex-basis: 460px;
  }

  .Footer__Block--newsletter {
    -ms-flex-preferred-size: 375px;
    flex-basis: 375px;
  }
}
.GiftCard {
  text-align: center;
}

.GiftCard__Wrapper {
  position: relative;
  max-width: 400px;
  margin: 0 auto;
}

.GiftCard__Redeem {
  margin-bottom: 30px;
}

.GiftCard__IllustrationWrapper {
  position: relative;
  margin: 40px 0;
}

.GiftCard__CodeHolder {
  position: absolute;
  display: inline-block;
  margin: 0 auto;
  bottom: 20px;
  left: 50%;
  white-space: nowrap;
  padding: 12px 20px;
  background: #ffffff;
  border-radius: 3px;
  -webkit-transform: translateX(-50%);
  transform: translateX(-50%);
}

.GiftCard__QrCode {
  margin: 20px 0;
}

.GiftCard__QrCode img {
  margin: 0 auto;
}
/**
 * ----------------------------------------------------------------------------
 * Main header
 * ----------------------------------------------------------------------------
 */

.shopify-section--header {
  position: relative;
  width: 100%;
  top: 0;
  left: 0;
  z-index: 5;
}

.Header .Heading,
.Header .Link--secondary,
.Header .Link--primary:hover {
  color: $header-heading-color;
}

.Header .Text--subdued,
.Header .Link--primary,
.Header .Link--secondary:hover {
  color: $header-light-text-color;
}

.Header {
  background: $header-background;
  color: $header-heading-color;
  -webkit-box-shadow: 0 -1px $header-border-color inset;
  box-shadow: 0 -1px $header-border-color inset;
  -webkit-transition: background 0.3s ease-in-out, -webkit-box-shadow 0.3s ease-in-out;
  transition: background 0.3s ease-in-out, -webkit-box-shadow 0.3s ease-in-out;
  transition: background 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
  transition: background 0.3s ease-in-out, box-shadow 0.3s ease-in-out, -webkit-box-shadow 0.3s ease-in-out;
}

.Header__Wrapper {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  padding: 15px 18px;
}

.Header__Logo {
  position: relative;
  margin-bottom: 0;
}

.Header__LogoLink,
.Header__LogoImage {
  display: block;
}

.Header__LogoImage {
  max-width: 90px;
  margin: 0 auto;
  -webkit-transition: opacity 0.3s ease-in-out;
  transition: opacity 0.3s ease-in-out;
}

.Header__LogoImage--transparent {
  position: absolute;
  top: 0;
  left: 0;
  opacity: 0;
}

.Header__Icon {
  display: block;
  line-height: 1;
  -webkit-transition: color 0.2s ease-in-out;
  transition: color 0.2s ease-in-out;
}

.supports-sticky .Header--transparent {
  background: transparent;

  .Header__LogoImage--primary:not(:only-child) {
    opacity: 0;
  }

  .Header__LogoImage--transparent {
    opacity: 1;
  }

  .Header__Icon svg {
    -webkit-filter: drop-shadow(0 1px rgba(#000000,0.25));
    filter: drop-shadow(0 1px rgba(#000000,0.25));
  }

  .Header__Icon,
  .Header__CurrencySelector,
  .HorizontalList__Item > .Heading,
  .Header__LogoLink > .Heading,
  .Text--subdued {
    color: currentColor;
  }
}

.Header__Icon .Icon--nav {
  height: 14px;
  width: 20px;
}

.Header__Icon .Icon--cart {
  width: 17px;
  height: 20px;
}

.Header__Icon .Icon--cart,
.Header__Icon .Icon--cart-desktop {
  position: relative;
  top: -1px; /* just because designer wants it... */
}

.Header__CartDot {
  position: absolute;
  top: 2px;
  right: -6px;
  width: 8px;
  height: 8px;
  border-radius: 100%;
  background-color: $header-heading-color;
  -webkit-box-shadow: 0 0 0 2px $header-background;
  box-shadow: 0 0 0 2px $header-background;
  -webkit-transform: scale(0);
  transform: scale(0);
  -webkit-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;
}

.Header__CartDot.is-visible {
  -webkit-transform: scale(1);
  transform: scale(1);
}

.Header--transparent .Header__CartDot {
  -webkit-box-shadow: none;
  box-shadow: none;
  background-color: currentColor;
}

@include av-mq('tablet-and-up') {
  .Header__Wrapper {
    padding: 18px 30px;
  }

  .Header__LogoImage {
    max-width: 100%;
  }

  .Header__Icon .Icon--nav-desktop {
    height: 17px;
    width: 24px;
  }

  .Header__Icon .Icon--cart-desktop {
    height: 23px;
    width: 19px;
  }
}

@include av-mq('desk') {
  .js .Header__Wrapper {
    opacity: 0;
    -webkit-transition: opacity 0.3s ease-in-out;
    transition: opacity 0.3s ease-in-out;
  }

  .Header:not(.Header--sidebar) .Header__Wrapper {
    padding: 18px 50px;
  }

  .Header__CurrencySelector {
    display: inline-block;
  }

  .Header:not(.Header--sidebar) .Header__FlexItem--fill {
    -webkit-box-flex: 1;
    -ms-flex: 1 0 0px;
    flex: 1 0 0;
  }

  .Header__FlexItem:last-child {
    text-align: right;
  }

  .Header--inline {
    .Header__FlexItem:first-child .Header__CurrencySelector {
      display: none;
    }
  }

  .Header--center {
    .Header__Wrapper.Header__Wrapper { /* Ugly hack to increase CSS precedence */
      padding-bottom: 24px;
    }

    .Header__MainNav {
      position: absolute;
      bottom: 0;
      left: 0;
      padding-bottom: 18px;
      width: 100%;
      text-align: center;
    }

    /* Ugly hack !! */
    .Header__MainNav .HorizontalList {
      margin-left: 0;
      margin-right: 0;
    }

    .Header__FlexItem {
      margin-bottom: 40px;
    }

    .Header__FlexItem:last-child .Header__CurrencySelector {
      display: none;
    }
  }

  .Header--initialized .Header__Wrapper {
    opacity: 1;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Desktop nav
 * ----------------------------------------------------------------------------
 */

.Header__LinkSpacer {
  position: absolute;
  display: block;
  bottom: 0;
  color: transparent;
  pointer-events: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;

  &::after {
    position: absolute;
    content: '';
    bottom: 0;
    left: 0;
    width: 100%;
    opacity: 0;
    -webkit-transform: scale(0, 1);
    transform: scale(0, 1);
    -webkit-transform-origin: left center;
    transform-origin: left center;
    border-bottom: 2px solid $header-heading-color;
    -webkit-transition: opacity 0.3s, -webkit-transform 0.3s;
    transition: opacity 0.3s, -webkit-transform 0.3s;
    transition: transform 0.3s, opacity 0.3s;
    transition: transform 0.3s, opacity 0.3s, -webkit-transform 0.3s;
  }
}

.HorizontalList__Item.is-expanded .Header__LinkSpacer::after,
.HorizontalList__Item.is-active .Header__LinkSpacer::after {
  opacity: 1;
  -webkit-transform: scale(1, 1);
  transform: scale(1, 1);
}

/**
 * ----------------------------------------------------------------------------
 * Dropdown menu
 * ----------------------------------------------------------------------------
 */

.DropdownMenu {
  position: absolute;
  visibility: hidden;
  opacity: 0;
  top: 100%;
  padding: 25px 0;
  min-width: 200px;
  max-width: 270px;
  width: -webkit-max-content;
  width: -moz-max-content;
  width: max-content;
  text-align: left;
  background: $header-background;
  border: 1px solid $header-border-color;
  border-top: none;
  -webkit-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;

  &::before {
    content: '';
    position: absolute;
    bottom: 100%;
    left: 0;
    background: $header-heading-color;
    width: 100%;
    height: 2px;
    -webkit-transform: scale(0, 1);
    transform: scale(0, 1);
    -webkit-transform-origin: left center;
    transform-origin: left center;
    -webkit-transition: -webkit-transform 0.3s;
    transition: -webkit-transform 0.3s;
    transition: transform 0.3s;
    transition: transform 0.3s, -webkit-transform 0.3s;
  }
}

.DropdownMenu[aria-hidden="false"] {
  opacity: 1;
  visibility: visible;

  &::before {
    -webkit-transform: scale(1, 1);
    transform: scale(1, 1);
  }
}

.DropdownMenu[aria-hidden="false"] .DropdownMenu {
  display: block;
}

.DropdownMenu [aria-haspopup] {
  position: relative;
}

.DropdownMenu .Link {
  padding-left: 25px;
  padding-right: 40px;
}

.DropdownMenu svg {
  position: absolute;
  width: 6px;
  top: calc(50% - 4px);
  height: 10px;
  right: 20px;
  -webkit-transition: -webkit-transform 0.2s ease-in-out;
  transition: -webkit-transform 0.2s ease-in-out;
  transition: transform 0.2s ease-in-out;
  transition: transform 0.2s ease-in-out, -webkit-transform 0.2s ease-in-out;
}

.DropdownMenu .Linklist__Item:hover {
  svg {
    -webkit-transform: translateX(4px);
    transform: translateX(4px);
  }

  > .Link--secondary {
    color: $header-light-text-color;
  }
}

.DropdownMenu .DropdownMenu {
  display: none;
  left: 100%;
  top: -26px;
  border-top: 1px solid $header-border-color;

  &::before {
    display: none;
  }
}

.DropdownMenu .DropdownMenu--reversed {
  left: auto;
  right: 100%;
}

/**
 * ----------------------------------------------------------------------------
 * Mega menu
 * ----------------------------------------------------------------------------
 */

.MegaMenu {
  position: absolute;
  padding: 20px 0;
  width: 100%;
  left: 0;
  top: 100%;
  visibility: hidden;
  opacity: 0;
  max-height: 600px;
  overflow: auto;
  overscroll-behavior: contain;
  text-align: left;
  background: $header-background;
  border-bottom: 1px solid $header-border-color;
  -webkit-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;

  @supports (--css: variables) {
    max-height: calc(100vh - var(--header-height));
  }
}

.MegaMenu[aria-hidden="false"] {
  opacity: 1;
  visibility: visible;
}

.MegaMenu__Inner {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  -webkit-box-align: start;
  -ms-flex-align: start;
  align-items: flex-start;
  -ms-flex-wrap: nowrap;
  flex-wrap: nowrap;
  max-width: 1450px;
  margin: 0 auto;
  padding: 0 10px; /* each menu has 40px margin, but header has 50px, so we normalize it here */
}

.MegaMenu--spacingEvenly .MegaMenu__Inner {
  -ms-flex-pack: distribute;
  justify-content: space-around;
  -webkit-box-pack: space-evenly;
  -ms-flex-pack: space-evenly;
  justify-content: space-evenly; /* space-evenly is not supported everywhere */
}

.MegaMenu--spacingCenter .MegaMenu__Inner {
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
}

.MegaMenu--grid .MegaMenu__Inner {
  @supports (display: grid) {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  }
}

.MegaMenu__Item {
  margin: 20px 40px;
  -ms-flex-negative: 1;
  flex-shrink: 1;
}

.MegaMenu__Item--fit {
  -ms-flex-negative: 0;
  flex-shrink: 0;
}

.MegaMenu__Title {
  display: block;
  margin-bottom: 20px;
}

.MegaMenu__Push {
  display: inline-block;
  text-align: center;
  vertical-align: top;
  width: 100%;
}

.MegaMenu__Push--shrink {
  width: 50%;
}

.MegaMenu__Push--shrink:first-child {
  padding-right: 15px;
}

.MegaMenu__Push--shrink:last-child {
  padding-left: 15px;
}

.MegaMenu__PushImageWrapper {
  margin: 8px auto 20px auto;
  max-width: 100%;
  overflow: hidden;
}

.MegaMenu__PushHeading {
  margin-bottom: 6px;
}

@media (-moz-touch-enabled: 0), (hover: hover) {
  .MegaMenu__Push img {
    -webkit-transform: scale(1);
    transform: scale(1);
    -webkit-transition: opacity 0.3s ease, -webkit-transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    transition: opacity 0.3s ease, -webkit-transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    transition: opacity 0.3s ease, transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    transition: opacity 0.3s ease, transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94), -webkit-transform 8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  }

  .MegaMenu__Push:hover img {
    -webkit-transform: scale(1.2);
    transform: scale(1.2);
  }
}
/**
 * ----------------------------------------------------------------------------
 * Image with text overlay section
 * ----------------------------------------------------------------------------
 */

.ImageHero {
  position: relative;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: horizontal;
  -webkit-box-direction: normal;
  -ms-flex-direction: row;
  flex-direction: row;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  text-align: center;
  background-size: cover;
  background-position: center;
  min-height: 380px;
  width: 100%;
  overflow: hidden;
}

.ImageHero--small {
  min-height: 330px;
}

.ImageHero--large {
  min-height: 480px;
}

.ImageHero__ImageWrapper,
.ImageHero__Image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
}

@include av-mq('lap-and-up') {
  @media (-moz-touch-enabled: 0), (hover: hover) {
    .ImageHero__Image--parallax {
      background-attachment: fixed;
    }
  }
}

.ImageHero__ImageWrapper--hasOverlay::before {
  position: absolute;
  content: '';
  height: 100%;
  width: 100%;
  left: 0;
  top: 0;
}

.ImageHero__Wrapper {
  z-index: 1;
}

.ImageHero__ContentOverlay {
  position: relative;
  -ms-flex-preferred-size: 425px;
  flex-basis: 425px;
  -webkit-box-flex: 0;
  -ms-flex-positive: 0;
  flex-grow: 0;
  padding: 0 15px;
  text-shadow: 0 1px rgba(#000000, 0.5);
}

.ImageHero__TextContent {
  position: absolute;
  padding: 0 24px;
  margin-bottom: 0 !important;
  top: 50%;
  left: 50%;
  width: 100%;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  text-align: center;
}

/* We allow embedding a video within an image hero */

.ImageHero iframe {
  position: absolute;
  height: 100%;
  width: 200%;
  left: -50%;
  pointer-events: none;
}

.ImageHero__Block {
  margin: 40px auto;
  padding: 38px 20px;
  max-width: 250px;
  -webkit-box-shadow: 0 1px 20px rgba(#363636, 0.3);
  box-shadow: 0 1px 20px rgba(#363636, 0.3);
}

.ImageHero__Block--small {
  max-width: 165px;
}

.ImageHero__Block--large {
  max-width: 320px;
}

.ImageHero__BlockHeading {
  margin: -0.325em 0 18px 0;
}

.ImageHero__BlockContent + .ImageHero__BlockLink {
  margin-top: 18px;
}

@include av-mq('phone') {
  .ImageHero__Block {
    font-size: to-size(11px);
  }
}

@include av-mq('tablet-and-up') {
  .ImageHero {
    min-height: 450px;
  }

  .ImageHero--small {
    min-height: 400px;
  }

  .ImageHero--large {
    min-height: 500px;
  }

  .ImageHero iframe {
    width: 100%;
    height: 200%;
    left: 0;
  }

  .ImageHero__Block {
    padding: 48px 15px;
    max-width: 380px;
  }

  .ImageHero__Block--small {
    max-width: 240px;
  }

  .ImageHero__Block--large {
    max-width: 520px;
  }

  .ImageHero__TextContent {
    padding: 0 40px;
    bottom: 40px;
    top: auto;
    left: 0;
    -webkit-transform: none;
    transform: none;
    text-align: left;
  }
}

@include av-mq('desk') {
  .ImageHero {
    min-height: 500px;
  }

  .ImageHero--small {
    min-height: 450px;
  }

  .ImageHero--large {
    min-height: 600px;
  }

  .ImageHero__TextContent {
    padding: 0 50px;
    bottom: 50px;
  }
}
/**
 * ----------------------------------------------------------------------------
 * Instagram feed
 * ----------------------------------------------------------------------------
 */

.Instafeed {
  height: 250px;
}

.Instafeed__Cell {
  width: 250px;
  margin: 0 5px;
  overflow: hidden;
}

.Instafeed__Image {
  position: relative;
  display: block;
  height: 100%;
  background-size: cover;
  background-position: center center;
}

.Instafeed__Overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  padding: 25px;
  background: $heading-color;
  color: $light-background;
  text-align: left;
  opacity: 0;
  -webkit-transition: opacity 0.2s ease-in-out;
  transition: opacity 0.2s ease-in-out;
}

.Instafeed__LikeCount {
  font-size: to-size(13px);

  svg {
    margin-right: 8px;
    width: 17px;
    height: 15px;
    vertical-align: sub;
  }
}

.Instafeed__Caption {
  position: relative;
  height: 6.6em; /* this is four times the default line height */
  margin: 20px 0;
  overflow: hidden;
  word-break: break-word;

  &::after {
    position: absolute;
    content: '';
    right: 0;
    bottom: 0;
    width: 70%;
    height: 1.6em;
    text-align: right;
    background: -webkit-gradient(linear, left top, right top, from(rgba($heading-color, 0)), color-stop(50%, $heading-color));
    background: linear-gradient(to right, rgba($heading-color, 0), $heading-color 50%);
  }
}

.Instafeed__Date {
  position: absolute;
  bottom: 18px;
  color: inherit;
  text-transform: uppercase;
}

@media (-moz-touch-enabled: 0), (hover: hover) {
  .Instafeed__Cell:hover .Instafeed__Overlay {
    opacity: 1;
  }
}

@include av-mq('pocket') {
  .Instafeed .flickity-prev-next-button {
    display: none;
  }
}

@include av-mq('tablet-and-up') {
  .Instafeed {
    height: calc(100vw / 2 - 70px);
  }

  .Instafeed__Cell {
    width: calc(100vw / 2 - 70px);
  }
}

@include av-mq('lap-and-up') {
  .Instafeed {
    height: calc(100vw / 3 - 60px);
  }

  .Instafeed__Cell {
    width: calc(100vw / 3 - 60px);
  }

  .Instafeed .flickity-prev-next-button.previous {
    top: calc(50% - (45px / 2));
    left: 25px;
  }

  .Instafeed .flickity-prev-next-button.next {
    top: calc(50% - (45px / 2));
    right: 25px;
  }
}

@include av-mq('desk') {
  .Instafeed {
    height: calc(100vw / 3 - 180px);
  }

  .Instafeed__Cell {
    width: calc(100vw / 3 - 180px);
  }
}

@include av-mq('widescreen') {
  .Instafeed__Caption {
    height: 9.9em; /* this is six times the default line height */
  }
}
.NewsletterPopup {
  position: fixed;
  bottom: 15px;
  left: 15px;
  width: calc(100% - 30px);
  padding: 24px 30px 30px 30px;
  background: $newsletter-popup-background;
  color: $newsletter-popup-text-color;
  z-index: 50;
  text-align: center;
  -webkit-box-shadow: 0 1px 4px rgba(#000000, 0.3);
  box-shadow: 0 1px 4px rgba(#000000, 0.3);
  visibility: hidden;
  -webkit-transform: translateY(25px);
  transform: translateY(25px);
  opacity: 0;
  -webkit-transition: all 0.5s $drawer-transition-timing;
  transition: all 0.5s $drawer-transition-timing;

  .Heading {
    color: inherit;
  }

  .Form__Input::-webkit-input-placeholder {
    color: rgba($newsletter-popup-text-color, 0.6);
  }

  .Form__Input:-ms-input-placeholder {
    color: rgba($newsletter-popup-text-color, 0.6);
  }

  .Form__Input::placeholder {
    color: rgba($newsletter-popup-text-color, 0.6);
  }

  .Form__Input {
    border-color: rgba($newsletter-popup-text-color, 0.4);
  }

  .Form__Input:focus {
    border-color: $newsletter-popup-text-color;
  }

  .Button {
    color: $newsletter-popup-background;
    border-color: $newsletter-popup-text-color;

    &::before {
      background-color: $newsletter-popup-text-color;
    }

    @media (-moz-touch-enabled: 0), (hover: hover) {
      &:not([disabled]):hover {
        color: $newsletter-popup-text-color;
        background-color: transparent;
      }
    }
  }
}

.NewsletterPopup[aria-hidden="false"] {
  -webkit-transform: translateY(0);
  transform: translateY(0);
  opacity: 1;
  visibility: visible;
}

.NewsletterPopup__Close {
  position: absolute;
  right: 15px;
  top: 15px;

  svg {
    display: block;
    width: 15px;
    height: 15px;
  }
}

.NewsletterPopup__Content a {
  text-decoration: underline;
  text-underline-position: under;
}

.NewsletterPopup__Form {
  margin-top: 32px;
}

@include av-mq('tablet-and-up') {
  .NewsletterPopup {
    max-width: 385px;
    right: 25px;
    bottom: 25px;
    left: auto;
    padding-top: 35px;
  }

  .NewsletterPopup__Close svg {
    width: 18px;
    height: 18px;
  }
}
.Password {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  padding: 24px;
  width: 100%;
  min-height: 100vh;
  background-size: cover;
  background-position: center;
}

@supports (--css: variables) {
  @include av-mq('pocket') {
    .Password {
      min-height: var(--window-height);
    }
  }
}

/**
 * ----------------------------------------------------------------------------
 * Header
 * ----------------------------------------------------------------------------
 */

.Password__Header {
  position: relative;
  text-align: center;
}

.Password__Logo {
  display: block;
  line-height: 1;
}

.Password__LogoImage {
  vertical-align: middle;
}

.Password__LockAction {
  position: absolute;
  right: 0;
  top: 50%;
  -webkit-transform: translateY(-50%);
  transform: translateY(-50%);

  svg {
    margin-left: 10px;
    width: 20px;
    height: 20px;
    vertical-align: bottom;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Content
 * ----------------------------------------------------------------------------
 */

.Password__Content {
  width: 470px;
  max-width: 100%;
  margin: 35px auto;
}

.Password__Newsletter {
  margin-bottom: 10px;
}

.Password__Card {
  padding: 24px;
  background: $light-background;
  text-align: center;
}

.Password__Message {
  font-size: to-size(13px);
}

.Password__Form {
  margin-top: 28px;
}

.Password__Form .Button {
  -webkit-box-flex: 0;
  -ms-flex: none;
  flex: none;
  margin-bottom: 0;
  margin-top: 15px;
  width: 100%;
}

.Password__Social {
  padding: 22px 25px 22px 28px;
  background: $background;
  text-align: center;
}

.Password__ShareButtons {
  margin-top: 15px;
}

@include av-mq('tablet-and-up') {
  .Password__Content {
    margin: 80px auto;
  }

  .Password__Card {
    padding: 45px 60px 50px 60px;
  }

  .Password__Form .Button {
    width: auto;
    margin-top: 0;
  }

  .Password__Social {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-pack: justify;
    -ms-flex-pack: justify;
    justify-content: space-between;
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
    text-align: left;
  }

  .Password__ShareButtons {
    margin-top: 0;
    margin-left: 15px;
    -ms-flex-negative: 0;
    flex-shrink: 0;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Footer
 * ----------------------------------------------------------------------------
 */

.Password__Footer {
  text-align: center;
}

.Password__AdminLink {
  display: block;
  margin-top: 15px;
}

.Password__Footer svg {
  width: 70px;
  height: 20px;
  vertical-align: bottom;
  margin-left: 2px;
}

@include av-mq('tablet-and-up') {
  .Password__Footer {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-pack: justify;
    -ms-flex-pack: justify;
    justify-content: space-between;
    text-align: left;
  }

  .Password__AdminLink {
    margin-top: 0;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Modal
 * ----------------------------------------------------------------------------
 */

.Password__Modal {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
}
/**
 * ----------------------------------------------------------------------------
 * Product (general)
 * ----------------------------------------------------------------------------
 */

.Product {
  position: relative;
  margin: 0 auto 50px auto;
}

@include av-mq('tablet-and-up') {
  .Product {
    margin-bottom: 80px;
  }
}

@include av-mq('lap-and-up') {
  .Product__Wrapper {
    max-width: calc(100% - 525px);
    margin-left: 0;
  }
}

@include av-mq('desk') {
  .Product__Wrapper {
    max-width: calc(100% - 550px);
  }

  .Product--small {
    max-width: 1200px;
  }

  .Product--medium {
    max-width: 1300px;
  }

  .Product--large {
    max-width: 1450px;
  }
}

@include av-mq('widescreen') {
  .Product__Wrapper {
    max-width: calc(100% - 500px);
  }

  .Product--fill .Product__Wrapper {
    max-width: calc(100% - 600px);
  }
}

/**
 * ----------------------------------------------------------------------------
 * Product gallery
 * ----------------------------------------------------------------------------
 */

.Product__Gallery {
  position: relative;
  margin-bottom: 28px;
}

.Product__Slideshow::after {
  content: 'flickity';
  display: none;
}

.Product__SlideItem {
  position: relative;
}

.Product__SlideItem--video {
  cursor: pointer;

  .Video__PlayButton {
    position: absolute;
    top: 50%;
    left: 50%;
    -webkit-transform: translate(-50%, -50%);
    transform: translate(-50%, -50%);
    color: #ffffff;
  }

  .Video__PlayButton svg {
    -webkit-transition: -webkit-transform 0.2s ease-in-out;
    transition: -webkit-transform 0.2s ease-in-out;
    transition: transform 0.2s ease-in-out;
    transition: transform 0.2s ease-in-out, -webkit-transform 0.2s ease-in-out;
  }

  &:hover .Video__PlayButton svg {
    -webkit-transform: scale(1.1);
    transform: scale(1.1);
  }
}

.Product__Video {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: #000000;
}

.Product__SlideshowNav {
  display: none;
}

@include av-mq('tablet-and-up') {
  .Product__Gallery {
    margin-bottom: 65px;
  }
}

@include av-mq('lap-and-up') {
  .Product__Gallery {
    margin-left: 50px;
  }

  .Product__SlideshowNav--dots {
    display: block;
  }

  .Product--fill .Product__Gallery--withDots {
    margin-left: 0;
  }

  .Product__Slideshow::after {
    content: ''; /* Disable Flickity */
  }

  .Product__SlideItem {
    display: block !important;
    margin-bottom: 30px;

    &:last-child {
      margin-bottom: 0;
    }
  }

  .Product__Slideshow--zoomable .Product__SlideItem--image {
    cursor: url($cursor-zoom-in-svg) 18 18, -webkit-zoom-in;
    cursor: url($cursor-zoom-in-svg) 18 18, zoom-in;
    cursor: -webkit-image-set(url($cursor-zoom-in-svg) 1x, url($cursor-zoom-in-2x-svg) 2x), -webkit-zoom-in;
    cursor: -webkit-image-set(url($cursor-zoom-in-svg) 1x, url($cursor-zoom-in-2x-svg) 2x), zoom-in;
  }

  /* On desktop we use a different apparition effect than fade in */
  .Product__Slideshow .Image--fadeIn {
    -webkit-transform: translateY(50px);
    transform: translateY(50px);
    opacity: 0;
    -webkit-transition: opacity 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94), -webkit-transform 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    transition: opacity 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94), -webkit-transform 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    transition: transform 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94), opacity 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    transition: transform 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94), opacity 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94), -webkit-transform 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  }

  .Product__Slideshow .Image--lazyLoaded.Image--fadeIn {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    opacity: 1;
  }

  .Product__SlideItem--video {
    .Video__PlayButton {
      -webkit-transform: translate(-50%, calc(-50% + 50px));
      transform: translate(-50%, calc(-50% + 50px));
      opacity: 0;
      -webkit-transition: opacity 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94), -webkit-transform 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94);
      transition: opacity 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94), -webkit-transform 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94);
      transition: transform 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94), opacity 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94);
      transition: transform 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94), opacity 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94), -webkit-transform 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    }

    .Image--lazyLoaded ~ .Video__PlayButton {
      -webkit-transform: translate(-50%, -50%);
      transform: translate(-50%, -50%);
      opacity: 1;
    }
  }

  .Product__SlideshowNav {
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    z-index: 1;
  }

  /* Dots */

  .Product__SlideshowNav--dots {
    left: -30px;
  }

  .Product--fill .Product__SlideshowNav--dots {
    left: 20px;
  }

  .Product__SlideshowNav--dots .Product__SlideshowNavScroller {
    position: -webkit-sticky;
    position: sticky;
    top: 50%;
    -webkit-transform: translateY(-50%);
    transform: translateY(-50%);

    @supports (--css: variables) {
      top: calc(50% + (var(--header-height) / 2));
    }
  }

  .Product__SlideshowNavDot {
    display: block;
    height: 10px;
    width: 10px;
    border-radius: 100%;
    border: 2px solid $border-color;
    background: transparent;
    -webkit-transition: all 0.2s ease-in-out;
    transition: all 0.2s ease-in-out;

    &:not(:last-child) {
      margin-bottom: 12px;
    }
  }

  .Product__SlideshowNavDot.is-selected {
    border-color: $heading-color;
    background: $heading-color;
  }

  /* Thumbnails */

  .Product__SlideshowNav--thumbnails {
    position: -webkit-sticky;
    position: sticky;
    padding: 50px 0;
    top: $header-base-height;
    margin-bottom: -50px;
    width: 70px;

    @supports (--css: variables) {
      top: var(--header-height);
    }
  }

  .Product__SlideshowNavImage {
    display: block;
    border: 1px solid transparent;
    -webkit-transition: all 0.2s ease-in-out;
    transition: all 0.2s ease-in-out;

    &:not(:last-child) {
      margin-bottom: 18px;
    }
  }

  .Product__SlideshowNavImage.is-selected {
    border-color: $heading-color;
  }

  .Product__SlideshowNavPlay {
    position: absolute;
    left: 50%;
    top: 50%;
    -webkit-transform: translate(-50%, -50%);
    transform: translate(-50%, -50%);
    color: #ffffff;
    -webkit-filter: drop-shadow(0 2px 2px rgba(#000000, 0.2));
    filter: drop-shadow(0 2px 2px rgba(#000000, 0.2));

    svg {
      width: 30px;
      height: 30px;
      -webkit-transition: -webkit-transform 0.2s ease-in-out;
      transition: -webkit-transform 0.2s ease-in-out;
      transition: transform 0.2s ease-in-out;
      transition: transform 0.2s ease-in-out, -webkit-transform 0.2s ease-in-out;
    }
  }

  .Product__SlideshowNavImage--video:hover svg {
    -webkit-transform: scale(1.1);
    transform: scale(1.1);
  }
}

@include av-mq('desk') {
  .Product__Gallery {
    margin-bottom: 80px;
  }

  .Product__Gallery--withThumbnails {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;

    .Product__Slideshow,
    .Product__SlideshowNav {
      -webkit-box-flex: 1;
      -ms-flex: 1 0 auto;
      flex: 1 0 auto;
    }

    .Product__SlideshowNav {
      -webkit-box-flex: 0;
      -ms-flex-positive: 0;
      flex-grow: 0;
    }

    .Product__SlideshowNav--thumbnails {
      display: none;
    }

    .Product__Slideshow {
      padding-top: 50px;
      margin-left: 50px;
    }

    .Product__SlideshowNav--dots {
      display: none;
    }

    .Product__SlideshowNav--thumbnails {
      display: block;
    }
  }
}

@include av-mq('widescreen') {
  .Product--fill .Product__Gallery--withThumbnails {
    margin-left: 100px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Product aside and info
 * ----------------------------------------------------------------------------
 */

.Product__Info,
.Product__Aside {
  max-width: 500px;
  margin: 0 auto;
}

.Product__Info--noGallery {
  padding-top: 24px;
}

@include av-mq('tablet-and-up') {
  .Product__Info .Container {
    padding-left: 0;
    padding-right: 0;
  }

  .Product__Aside .Section {
    max-width: 630px;
    margin: 0 auto;
  }
}

@include av-mq('lap-and-up') {
  .Product__InfoWrapper {
    position: absolute;
    right: 0;
    top: 0;
    height: 100%;
  }

  .Product__Info {
    position: -webkit-sticky;
    position: sticky;
    top: $header-base-height;
    right: 0;
    width: 375px;
    margin: 0 100px -40px 50px;
    padding-top: 65px;
    padding-bottom: 40px;

    @supports (--css: variables) {
      top: var(--header-height);
    }
  }

  .Product__Info--noGallery {
    padding-top: 0;
  }

  .Product__Aside {
    max-width: 820px;
    padding-left: 50px;
  }

  .Product--fill .Product__Aside {
    padding-right: 50px;
  }

  .Product__Aside .SectionHeader {
    margin-bottom: 30px;
  }
}

@include av-mq('desk') {
  .Product__Info {
    width: 400px;
  }
}

@include av-mq('widescreen') {
  .Product__Info {
    margin-right: 50px;
  }

  .Product--fill .Product__Info {
    margin-right: 150px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Action list
 * ----------------------------------------------------------------------------
 */

@-webkit-keyframes shareItemAnimation {
  0% {
    -webkit-transform: translateY(0%);
    transform: translateY(0%);
  }

  25% {
    opacity: 0;
    -webkit-transform: translateY(100%);
    transform: translateY(100%);
  }

  50% {
    opacity: 0;
    -webkit-transform: translateY(-100%);
    transform: translateY(-100%);
  }

  75% {
    opacity: 1;
    -webkit-transform: translateY(0%);
    transform: translateY(0%);
  }
}

@keyframes shareItemAnimation {
  0% {
    -webkit-transform: translateY(0%);
    transform: translateY(0%);
  }

  25% {
    opacity: 0;
    -webkit-transform: translateY(100%);
    transform: translateY(100%);
  }

  50% {
    opacity: 0;
    -webkit-transform: translateY(-100%);
    transform: translateY(-100%);
  }

  75% {
    opacity: 1;
    -webkit-transform: translateY(0%);
    transform: translateY(0%);
  }
}

.Product__ActionList {
  position: absolute;
  top: 30px;
  right: 25px;
  z-index: 1;
  visibility: visible;
  opacity: 1;
  -webkit-transition: visibility 0.2s ease-in-out, opacity 0.2s ease-in-out;
  transition: visibility 0.2s ease-in-out, opacity 0.2s ease-in-out;
}

.Product__ActionList.is-hidden {
  opacity: 0;
  visibility: hidden;
}

.Product__ActionItem {
  display: block;
  position: relative;
}

.Product__ActionItem + .Product__ActionItem {
  margin-top: 15px;
}

.Product__ShareList {
  display: block;
  position: absolute;
  visibility: hidden;
  top: 100%;
  right: 0;
  color: $text-color;
}

.Product__ActionItem .Icon--share {
  margin-left: -1px;
}

.Product__ShareItem {
  display: block;
  margin: 15px 0 15px auto;
  padding: 7px 15px 7px 17px;
  width: -webkit-fit-content;
  width: -moz-fit-content;
  width: fit-content;
  background: $light-background;
  border-radius: 25px;
  font-size: to-size(13px);
  white-space: nowrap;
  opacity: 0;
  -webkit-box-shadow: 0 2px 10px rgba(#363636, 0.15);
  box-shadow: 0 2px 10px rgba(#363636, 0.15);
  -webkit-transition: all 0.45s cubic-bezier(0.645, 0.045, 0.355, 1) 0.2s;
  transition: all 0.45s cubic-bezier(0.645, 0.045, 0.355, 1) 0.2s;

  &:active,
  &:focus {
    color: $light-background;
    background: $text-color;
    outline: none;
  }

  &:nth-child(2) {
    -webkit-transition-delay: 0.1s;
    transition-delay: 0.1s;
  }

  &:nth-child(3) {
    -webkit-transition-delay: 0s;
    transition-delay: 0s;
  }

  svg {
    margin-right: 12px;
    font-size: to-size(14px);
    vertical-align: sub;
    -webkit-transform: translateZ(0);
    transform: translateZ(0);
  }

  &:hover svg {
    -webkit-animation: shareItemAnimation 0.5s ease-in-out forwards;
    animation: shareItemAnimation 0.5s ease-in-out forwards;
  }
}

.Product__ShareList[aria-hidden="false"] {
  visibility: visible;

  .Product__ShareItem {
    opacity: 1;
    -webkit-transition-delay: 0s;
    transition-delay: 0s;

    &:nth-child(2) {
      -webkit-transition-delay: 0.1s;
      transition-delay: 0.1s;
    }

    &:nth-child(3) {
      -webkit-transition-delay: 0.2s;
      transition-delay: 0.2s;
    }
  }
}

@include av-mq('lap-and-up') {
  .Product__ActionList {
    position: -webkit-sticky;
    position: sticky;
    float: right;
    top: calc(100vh - var(--header-height));
  }

  .no-supports-sticky .Product__ActionList {
    display: none;
  }

  .Product__ShareList {
    top: auto;
    bottom: 100%;
  }

  .Product__ShareItem {
    -webkit-transition-delay: 0s;
    transition-delay: 0s;

    &:nth-child(3) {
      -webkit-transition-delay: 0.2s;
      transition-delay: 0.2s;
    }
  }

  .Product__ShareList[aria-hidden="false"] .Product__ShareItem {
    -webkit-transition-delay: 0.2s;
    transition-delay: 0.2s;

    &:nth-child(3) {
      -webkit-transition-delay: 0s;
      transition-delay: 0s;
    }
  }
}

@include av-mq('widescreen') {
  .Product:not(.Product--fill) .Product__ActionList {
    margin-right: -80px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Product meta and info
 * ----------------------------------------------------------------------------
 */

.ProductMeta {
  text-align: center;
}

.ProductMeta__ImageWrapper {
  display: block;
  margin-bottom: 32px;
}

.ProductMeta__Vendor {
  margin-bottom: 20px;
}

.ProductMeta__Title {
  margin-bottom: 0;
}

.ProductMeta__PriceList {
  margin-top: 15px;
}

.ProductMeta__Price.Price--compareAt {
  margin-left: 30px;
}

.ProductMeta__Description {
  margin: 24px 0;
  padding-top: 24px;
  border-top: 1px solid $border-color;
  text-align: left;
}

/* When the description is set after the product form, layout changes a bit */
.ProductForm ~ .ProductMeta__Description {
  border-top: none;
  padding-top: 0;
}

.Product__QuickNav {
  position: relative;
  margin-top: 40px;
  border-top: 1px solid $border-color;
  border-bottom: 1px solid $border-color;

  a {
    display: block;
    padding: 11px 16px;
    -webkit-backface-visibility: hidden;
    backface-visibility: hidden;
    -webkit-transform: rotateX(0deg);
    transform: rotateX(0deg);
  }

  a:last-child {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    -webkit-transform: rotateX(180deg);
    transform: rotateX(180deg);
  }

  svg {
    position: absolute;
    right: 18px;
    top: calc(50% - 5px);
    height: 10px;
    width: 8px;
  }
}

.Product__QuickNavWrapper {
  -webkit-transition: 0.6s;
  transition: 0.6s;
  -webkit-transform-style: preserve-3d;
  transform-style: preserve-3d;
}

.Product__QuickNav.is-flipped .Product__QuickNavWrapper {
  -webkit-transform: rotateX(180deg);
  transform: rotateX(180deg);
}

@include av-mq('lap-and-up') {
  .ProductMeta {
    text-align: left;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Product form
 * ----------------------------------------------------------------------------
 */

.ProductForm {
  margin-top: 24px;
}

.ProductForm__Variants {
  margin-bottom: 25px;
}

.ProductForm__Option {
  position: relative;
  margin-bottom: 10px;
}

.no-js .ProductForm__Option:not(.no-js) {
  display: none;
}

.ProductForm__Item {
  position: relative;
  width: 100%;
  text-align: left;
  padding: 10px 28px 10px 14px;
  border: 1px solid $border-color;
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.ProductForm__Item .Icon--select-arrow {
  position: absolute;
  top: calc(50% - 5px);
  right: 15px;
  width: 10px;
  height: 10px;
}

.ProductForm__ColorSwatch {
  position: absolute;
  left: 5px;
  top: 50%;
  width: 32px;
  height: 32px;
  background-size: cover;
  -webkit-transform: translateY(-50%);
  transform: translateY(-50%);
}

.ProductForm__ColorSwatch--white {
  outline: 1px solid $border-color;
}

.ProductForm__SelectedValue {
  display: inline-block;
  white-space: nowrap;
  text-overflow: ellipsis;
  overflow: hidden;
  max-width: 220px;
  vertical-align: top;
}

.ProductForm__ColorSwatch + .ProductForm__SelectedValue {
  margin-left: 38px;
  max-width: 160px;
}

.ProductForm__OptionCount {
  float: right;
  margin-right: 14px;
}

.ProductForm__Inventory {
  margin-top: 8px;
  font-style: italic;
}

.ProductForm__Error {
  margin-top: 10px;
  text-align: center;
}

.ProductForm__AddToCart {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
}

/**
 * ----------------------------------------------------------------------------
 * Featured image
 * ----------------------------------------------------------------------------
 */

.Product__FeatureImageWrapper {
  overflow: hidden;
  background-size: cover;
}

.Product__FeatureImage {
  height: 415px;
  background-size: cover;
  background-position: center;
}

@include av-mq('tablet-and-up') {
  .Product__FeatureImage {
    height: 500px;
  }
}

@include av-mq('desk') {
  .Product__FeatureImage {
    height: 600px;
  }

  .Product__FeatureImage--small {
    height: 500px;
  }

  .Product__FeatureImage--large {
    height: 700px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Product tabs
 * ----------------------------------------------------------------------------
 */

.Product__Tabs {
  margin: 50px 0;
}

@include av-mq('phone') {
  .Product__Tabs .Collapsible__Content {
    padding-top: 6px;
    padding-bottom: 28px;
  }
}

@include av-mq('pocket') {
  .Product__Tabs .Collapsible {
    padding: 0 24px;
  }
}

@include av-mq('lap-and-up') {
  .Product__Tabs {
    margin: 80px 0;
  }

  .Product__Tabs .Collapsible__Content {
    padding-right: 80px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Variant slideshow (for color carousel)
 * ----------------------------------------------------------------------------
 */

@-webkit-keyframes variantSelectorInfoOpeningAnimation {
  0% {
    -webkit-transform: translateY(10px);
    transform: translateY(10px);
    opacity: 0;
  }

  50% {
    -webkit-transform: translateY(10px);
    transform: translateY(10px);
    opacity: 0;
  }

  100% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    opacity: 1;
  }
}

@keyframes variantSelectorInfoOpeningAnimation {
  0% {
    -webkit-transform: translateY(10px);
    transform: translateY(10px);
    opacity: 0;
  }

  50% {
    -webkit-transform: translateY(10px);
    transform: translateY(10px);
    opacity: 0;
  }

  100% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    opacity: 1;
  }
}

@-webkit-keyframes variantSelectorInfoClosingAnimation {
  0% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    opacity: 1;
  }

  100% {
    -webkit-transform: translateY(-10px);
    transform: translateY(-10px);
    opacity: 0;
  }
}

@keyframes variantSelectorInfoClosingAnimation {
  0% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    opacity: 1;
  }

  100% {
    -webkit-transform: translateY(-10px);
    transform: translateY(-10px);
    opacity: 0;
  }
}

.VariantSelector {
  position: fixed;
  width: 100%;
  bottom: 0;
  left: 0;
  background: $background;
  padding: 24px 0;
  z-index: 10;
  -webkit-box-shadow: 0 -2px 10px rgba(#363636, 0.2);
  box-shadow: 0 -2px 10px rgba(#363636, 0.2);
  -webkit-transform: translateY(100%);
  transform: translateY(100%);
  visibility: hidden;
  -webkit-transition: visibility 0.4s cubic-bezier(0.645, 0.045, 0.355, 1), -webkit-transform 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  transition: visibility 0.4s cubic-bezier(0.645, 0.045, 0.355, 1), -webkit-transform 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  transition: transform 0.4s cubic-bezier(0.645, 0.045, 0.355, 1), visibility 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
  transition: transform 0.4s cubic-bezier(0.645, 0.045, 0.355, 1), visibility 0.4s cubic-bezier(0.645, 0.045, 0.355, 1), -webkit-transform 0.4s cubic-bezier(0.645, 0.045, 0.355, 1);
}

.VariantSelector[aria-hidden="false"] {
  -webkit-transform: translateY(0);
  transform: translateY(0);
  visibility: visible;
}

.VariantSelector__Item {
  padding: 0 10px;
  width: 60%;
}

.VariantSelector__Info {
  position: relative;
  margin: 48px 24px 0 24px;
}

.VariantSelector__ChoiceList {
  margin-bottom: 34px;
}

.VariantSelector__Choice {
  display: table;
  table-layout: fixed;
  width: 100%;
  -webkit-animation: 0.15s variantSelectorInfoClosingAnimation forwards ease-in-out;
  animation: 0.15s variantSelectorInfoClosingAnimation forwards ease-in-out;
}

.VariantSelector__Choice.is-selected {
  -webkit-animation: 0.3s variantSelectorInfoOpeningAnimation forwards ease-in-out;
  animation: 0.3s variantSelectorInfoOpeningAnimation forwards ease-in-out;
}

.VariantSelector__Choice:not(:first-child) {
  position: absolute;
  top: 0;
  left: 0;
}

.VariantSelector__ChoiceColor,
.VariantSelector__ChoicePrice {
  display: table-cell;
  width: 50%;
  text-align: center;
  vertical-align: middle;
}

.VariantSelector__ChoiceColor {
  border-right: 1px solid $border-color;
}

.VariantSelector__ColorSwatch {
  display: inline-block;
  width: 16px;
  height: 16px;
  margin-right: 15px;
  vertical-align: sub;
  background-size: cover;
}

.VariantSelector__ColorSwatch--white {
  outline: 1px solid $border-color;
}

.VariantSelector__ChoicePrice {
  font-size: to-size(11px);
}

@include av-mq('phone') {
  .VariantSelector .flickity-prev-next-button {
    display: none;
  }
}

@include av-mq('tablet-and-up') {
  /* Starting from tablet, the look and feel of this selector is completely different and look like a modal */
  .VariantSelector {
    top: 50%;
    bottom: auto;
    left: 50%;
    width: 80%;
    padding-bottom: 34px;
    max-height: 100%;
    max-width: 800px;
    opacity: 0;
    -webkit-transform: translate(-50%, -50%);
    transform: translate(-50%, -50%);
    -webkit-transition: all 0.3s ease-in-out;
    transition: all 0.3s ease-in-out;
    overflow: auto;
  }

  .VariantSelector[aria-hidden="false"] {
    -webkit-transform: translate(-50%, -50%);
    transform: translate(-50%, -50%);
    opacity: 1;
  }

  .VariantSelector__Item {
    padding: 0 25px;
    width: 46%;
  }

  .VariantSelector .flickity-prev-next-button.next {
    top: calc(50% - 45px);
    right: 20px;
  }

  .VariantSelector .flickity-prev-next-button.previous {
    top: calc(50% - 45px);
    left: 20px;
  }

  .VariantSelector__Info {
    max-width: 350px;
    margin-left: auto;
    margin-right: auto;
  }

  .VariantSelector__ChoicePrice {
    font-size: to-size(13px);
  }
}

@media (min-width: 800px) and (max-height: 950px) {
  .VariantSelector__ImageWrapper {
    max-width: 290px !important;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Featured product (on home page)
 * ----------------------------------------------------------------------------
 */

.FeaturedProduct__Gallery {
  display: block;
  margin-bottom: 20px;
}

.FeaturedProduct__ViewWrapper {
  margin-top: 34px;
  text-align: center;
}

@include av-mq('tablet-and-up') {
  .FeaturedProduct {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-align: start;
    -ms-flex-align: start;
    align-items: flex-start;
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    justify-content: center;
    max-width: 880px;
    margin: 0 auto;
  }

  .FeaturedProduct--center {
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
  }

  .FeaturedProduct__Gallery,
  .FeaturedProduct__Info {
    -webkit-box-flex: 1;
    -ms-flex: 1 1 50%;
    flex: 1 1 50%;
  }

  .FeaturedProduct__Gallery {
    margin: 0;
  }

  .FeaturedProduct__Info {
    margin-left: 50px;
  }

  .FeaturedProduct__Info .ProductMeta,
  .FeaturedProduct__ViewWrapper {
    text-align: left;
  }
}

@include av-mq('lap-and-up') {
  .FeaturedProduct__Info {
    margin-left: 80px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Shopify payment button
 * ----------------------------------------------------------------------------
 */

.shopify-payment-button {
  margin-top: 20px;
  text-align: center;
}

.shopify-payment-button__more-options {
  @extend .Link, .Link--underline;
  width: auto;
  line-height: normal;

  &[aria-hidden="true"] {
    display: none;
  }
}

.shopify-payment-button__more-options:hover:not([disabled]) {
  text-decoration: none;
}

.shopify-payment-button__button--unbranded {
  @extend .Button, .Button--primary;
}
/**
 * ----------------------------------------------------------------------------
 * Product reviews (integration with Shopify Reviews free app)
 * ----------------------------------------------------------------------------
 */

#shopify-product-reviews {
  margin: 18px 0 28px 0 !important;
  overflow: visible !important;

  .spr-header-title,
  .spr-summary-starrating,
  .spr-summary-caption,
  .spr-review-reportreview,
  .spr-pagination,
  .spr-form-title {
    display: none;
  }

  .spr-container {
    padding: 0;
    border: none;
  }

  .spr-container,
  .spr-content {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-orient: vertical;
    -webkit-box-direction: normal;
    -ms-flex-direction: column;
    flex-direction: column;
  }

  .spr-header,
  .spr-form {
    -webkit-box-ordinal-group: 3;
    -ms-flex-order: 2;
    order: 2;
  }

  .spr-content,
  .spr-reviews {
    -webkit-box-ordinal-group: 2;
    -ms-flex-order: 1;
    order: 1;
  }

  .spr-form {
    margin: -4px 0 0 0;
    padding: 0;
  }

  .spr-icon {
    font-size: to-size(10px);
  }

  .spr-form-input .spr-icon {
    font-size: to-size(14px);
  }

  .spr-icon + .spr-icon {
    margin-left: 3px;
  }

  .spr-icon-star-empty {
    opacity: 0.25;
  }

  .spr-icon-star-empty::before {
    content: '\e800';
  }

  .spr-starrating.spr-form-input-error a {
    color: inherit;
  }

  .spr-reviews {
    margin: -6px 0 35px 0;
  }

  .spr-review {
    position: relative;
    padding: 0 0 30px 0;
    border: none;
    margin: 0;
  }

  .spr-review + .spr-review {
    margin-top: 26px;
  }

  .spr-review-header {
    position: static;
    margin-bottom: 12px;
  }

  .spr-review-header-starratings {
    margin-bottom: 0;
  }

  .spr-review-header-title {
    font-family: $heading-font-family;
    font-weight: $heading-font-weight;
    font-style: $heading-font-style;
    font-size: to-size(11px);
    text-transform: uppercase;
    letter-spacing: 0.2em;
  }

  .spr-review-header-byline {
    position: absolute;
    bottom: 0;
    left: 0;
    margin-bottom: 0;
    font-style: normal;
    opacity: 1;
    color: $text-color-light;

    strong {
      font-weight: normal;
    }
  }

  .spr-review-content {
    margin-bottom: 0;
  }

  .spr-review-reply {
    margin: 18px 0 6px 0;
    padding: 0 0 0 14px;
    background: none;
    border-left: 3px solid $border-color;
    font-style: italic;
  }

  .spr-summary-actions {
    display: block;
  }

  .spr-review-reply-shop {
    float: none;
  }

  .spr-summary-actions-newreview,
  .spr-button-primary:not(input) {
    @extend .Button, .Button--primary;
    width: 100%;
  }

  input.spr-button-primary {
    @extend .Button;
    border-color: $button-background;
    background: $button-background;
    color: $button-text-color;
    width: 100%;
  }

  .spr-pagination-prev,
  .spr-pagination-next {
    display: block;
    position: relative;
    margin-bottom: 20px;
  }

  .spr-pagination-prev > a,
  .spr-pagination-next > a {
    @extend .Button, .Button--secondary;
    width: 100%;
  }

  .spr-form-message {
    @extend .Alert, .Form__Alert;
  }

  .spr-form-message-error {
    @extend .Alert--error;
  }

  .spr-form-message-success {
    @extend .Alert--success;
  }

  .spr-form-label {
    @extend .Form__Label;
  }

  .spr-form-input-text,
  .spr-form-input-email,
  .spr-form-input-textarea {
    @extend .Form__Input;
  }

  .new-review-form {
    margin-top: 20px;
  }

  .spr-form-contact-name,
  .spr-form-contact-email,
  .spr-form-contact-location,
  .spr-form-review-title,
  .spr-form-review-rating,
  .spr-form-review-body {
    margin-bottom: 15px;
  }
}

@include av-mq('tablet-and-up') {
  #shopify-product-reviews {
    margin: 8px 40px 28px 0 !important;

    .spr-review-header-title {
      font-size: to-size(12px);
    }

    .spr-review-header-byline,
    .spr-review-content-body {
      font-size: to-size(14px);
    }

    .spr-header {
      -ms-flex-item-align: start;
      align-self: flex-start;
      width: 100%;
    }

    .spr-summary-actions-newreview,
    .spr-button-primary:not(input),
    input.spr-button-primary,
    .spr-pagination-prev > a,
    .spr-pagination-next > a {
      width: auto;
      float: none;
    }

    .spr-form-contact-name,
    .spr-form-contact-email,
    .spr-form-contact-location,
    .spr-form-review-title,
    .spr-form-review-rating,
    .spr-form-review-body {
      margin-bottom: 25px;
    }

    .spr-summary-actions {
      display: -webkit-box;
      display: -ms-flexbox;
      display: flex;
    }

    .spr-pagination-prev,
    .spr-pagination-next {
      margin: 0 20px 0 0;
    }

    .spr-pagination-prev > a,
    .spr-pagination-next > a {
      display: block;
    }
  }
}

@include av-mq('lap-and-up') {
  #shopify-product-reviews {
    margin-bottom: 4px !important;
}


@include av-mq('desk') {
  #shopify-product-reviews {
    margin-right: 100px !important;
  }
}
.Search {
  display: block;
  padding: 30px 24px;
}

.Search[aria-hidden="false"] {
  visibility: visible;
  opacity: 1;
}

.Search__SearchBar {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
}

.Search__Form {
  -webkit-box-flex: 1;
  -ms-flex: 1 0 auto;
  flex: 1 0 auto;
}

.Search__Input {
  background: none;
  width: 100%;
  border: none;
  font-size: to-size(15px);
  vertical-align: middle;

  &::-webkit-input-placeholder {
    color: $text-color-light;
  }

  &:-ms-input-placeholder {
    color: $text-color-light;
  }

  &::placeholder {
    color: $text-color-light;
  }

  &::-ms-clear {
    display: none;
  }
}

.Search__Close {
  color: $text-color-light;
  font-size: to-size(15px);
  line-height: 1;
}

.Search__Results {
  margin-top: 50px;
}

@include av-mq('phone') {
  .Search__Results {
    .ProductItem__Wrapper {
      display: -webkit-box;
      display: -ms-flexbox;
      display: flex;
      -webkit-box-align: center;
      -ms-flex-align: center;
      align-items: center;
    }

    .Grid__Cell + .Grid__Cell {
      margin-top: 25px;
    }

    .ProductItem__ImageWrapper {
      width: 70px;
      margin-right: 25px;
    }

    .ProductItem__Info {
      margin-top: 0;
      text-align: left;
    }
  }
}

@include av-mq('tablet-and-up') {
  .Search {
    padding: 40px 50px;
  }

  .Search__Input {
    font-size: to-size(18px);
  }

  .Search__Close {
    font-size: to-size(16px);

    svg {
      stroke-width: 1.25px;
    }
  }

  .Search__Results {
    margin-top: 75px;
  }
}
@-webkit-keyframes shopTheLookDotKeyframe {
  0% {
    -webkit-transform: scale(1.0);
    transform: scale(1.0);
  }

  50% {
    -webkit-transform: scale(1.05);
    transform: scale(1.05);
  }

  100% {
    -webkit-transform: scale(1);
    transform: scale(1);
  }
}

@keyframes shopTheLookDotKeyframe {
  0% {
    -webkit-transform: scale(1.0);
    transform: scale(1.0);
  }

  50% {
    -webkit-transform: scale(1.05);
    transform: scale(1.05);
  }

  100% {
    -webkit-transform: scale(1);
    transform: scale(1);
  }
}

.ShopTheLook {
  z-index: 2;
}

.ShopTheLook__Item {
  padding: 0 5px;
  width: calc(100% - 40px);
  -webkit-transition: opacity 0.3s ease-in-out;
  transition: opacity 0.3s ease-in-out;
}

.ShopTheLook__Item.is-selected {
  z-index: 1;
}

.ShopTheLook__ImageWrapper {
  position: relative;
  max-width: 100%;
}

.ShopTheLook__Image {
  display: block;
  height: 100%;
  width: 100%;
}

.ShopTheLook__Dot {
  position: absolute;
  display: block;
  width: 16px;
  height: 16px;
  margin: -8px 0 0 -8px;
  background: #ffffff;
  border-radius: 100%;
  -webkit-box-shadow: 0 1px 10px rgba(#000000, 0.25);
  box-shadow: 0 1px 10px rgba(#000000, 0.25);
  cursor: pointer;
  z-index: 1;
  -webkit-transform: scale(1);
  transform: scale(1);
  -webkit-transition: -webkit-transform 0.25s ease-in-out;
  transition: -webkit-transform 0.25s ease-in-out;
  transition: transform 0.25s ease-in-out;
  transition: transform 0.25s ease-in-out, -webkit-transform 0.25s ease-in-out;

  &::after {
    position: absolute;
    content: '';
    width: 40px;
    height: 40px;
    left: -12px; /* This is 40/2 - 16/2 */
    top: -12px; /* This is 40/2 - 16/2 */
    border-radius: 100%;
    background: rgba(#ffffff, 0.4);
    -webkit-animation: 1.4s shopTheLookDotKeyframe ease-in-out infinite;
    animation: 1.4s shopTheLookDotKeyframe ease-in-out infinite;
  }
}

.ShopTheLook__Dot--dark {
  background: #000000;

  &::after {
    background: rgba(#000000, 0.4);
  }
}

.ShopTheLook__Dot.is-active,
.supports-hover .ShopTheLook__Dot:hover {
  -webkit-transform: scale(1.5);
  transform: scale(1.5);
}

.ShopTheLook__ProductItem .ProductItem__ImageWrapper {
  max-width: 150px;
  margin: 0 auto;
}

.ShopTheLook__DiscoverButtonWrapper {
  margin: 24px 24px 0 24px;
  text-align: center;
}

@include av-mq('phone') {
  .ShopTheLook__ViewButton {
    width: 100%;
  }

  .ShopTheLook__ProductItem--withHiddenInfo .ProductItem__Info {
    display: none;
  }

  .ShopTheLook__ProductItem {
    padding: 15px 0;
  }
}

@include av-mq('pocket') {
  .ShopTheLook > .flickity-viewport {
    -webkit-transition: opacity 0.3s ease-in-out, -webkit-transform 0.3s ease-in-out;
    transition: opacity 0.3s ease-in-out, -webkit-transform 0.3s ease-in-out;
    transition: transform 0.3s ease-in-out, opacity 0.3s ease-in-out;
    transition: transform 0.3s ease-in-out, opacity 0.3s ease-in-out, -webkit-transform 0.3s ease-in-out;
  }

  .ShopTheLook::before {
    content: '';
    position: fixed;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    background: $background;
    opacity: 0;
    visibility: hidden;
    -webkit-transition: all 0.25s ease-in-out;
    transition: all 0.25s ease-in-out;
  }

  .ShopTheLook.is-zoomed {
    &::before {
      opacity: 1;
      visibility: visible;
      -webkit-transition-delay: 0s;
      transition-delay: 0s;
    }

    .ShopTheLook__Item:not(.is-selected) {
      opacity: 0;
    }
  }

  .ShopTheLook__ProductItem {
    padding: 30px 0 40px 0;
  }
}

@include av-mq('tablet-and-up') {
  .ShopTheLook__DiscoverButtonWrapper {
    margin-top: 50px;
  }

  .ShopTheLook__Item {
    width: auto;
    padding: 0 15px;
  }

  .ShopTheLook__ProductItem .ProductItem__Wrapper {
    max-width: 250px;
    margin: 0 auto;
  }
}

@include av-mq('lap-and-up') {
  .ShopTheLook {
    max-width: 1480px;
    margin: 0 auto;
    padding: 0 130px;
  }

  .ShopTheLook__Item {
    width: 100%;
    padding: 0;
  }

  .ShopTheLook__Inner {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    justify-content: center;
    min-height: 550px;
  }

  .ShopTheLook__ImageWrapper {
    -webkit-box-flex: 0;
    -ms-flex: 0 1 auto;
    flex: 0 1 auto;
  }

  .ShopTheLook__Image {
    max-height: 100%;
    width: auto;
  }

  .ShopTheLook__ProductList {
    -webkit-box-flex: 0;
    -ms-flex: none;
    flex: none;
    width: 270px;
    margin: 0 80px;
  }

  .ShopTheLook__ProductItem .ProductItem__Wrapper {
    max-width: none;
  }

  .ShopTheLook__ProductItem .ProductItem__ImageWrapper {
    max-width: 250px;
  }

  .ShopTheLook__ViewButton {
    margin-top: 25px;
  }

  .ShopTheLook .flickity-prev-next-button {
    top: calc(50% - (45px / 2));
  }

  .ShopTheLook .flickity-prev-next-button.next {
    right: 40px;
  }

  .ShopTheLook .flickity-prev-next-button.previous {
    left: 40px;
  }
}
/**
 * ----------------------------------------------------------------------------
 * Sidebar
 * ----------------------------------------------------------------------------
 */

.SidebarMenu {
  height: 100%;
  background: $navigation-background;
  color: $navigation-text-color;
}

.SidebarMenu .Heading,
.supports-hover .SidebarMenu .Link--primary:hover {
  color: $navigation-text-color;
}

.SidebarMenu .Text--subdued {
  color: $navigation-text-color-light;
}

.SidebarMenu .Collapsible,
.SidebarMenu .Linklist {
  border-color: $navigation-border-color;
}

.SidebarMenu__Nav .Collapsible:first-child {
  border-top: none;
}

/* We need to do that to add extra padding for scroll, as Safari on Mac and iOS has some issue with directly adding a padding-bottom */
.SidebarMenu .Drawer__Main::after {
  display: block;
  content: '';
  height: 35px;
}

.SidebarMenu__Nav--secondary {
  margin-top: 28px;
}

.SidebarMenu .Drawer__Footer {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  width: 100%;
  min-height: 48px;
  -webkit-box-shadow: 0 1px $navigation-border-color inset;
  box-shadow: 0 1px $navigation-border-color inset;
  color: $navigation-text-color-light;
}

.SidebarMenu__CurrencySelector,
.SidebarMenu__Social {
  -webkit-box-flex: 1;
  -ms-flex: 1 0 auto;
  flex: 1 0 auto;
  margin: 0;
  padding: 6px 0;
}

.SidebarMenu__CurrencySelector {
  width: 120px;
  -webkit-box-flex: 0;
  -ms-flex: none;
  flex: none;
  text-align: center;
  font-size: to-size(11px);

  .Select {
    display: inline-block;
  }
}

/* All this code is pretty ugly hack just to comply with some Shopify strict rules... */
.SidebarMenu__Social {
  @supports (display: grid) {
    display: grid;
    grid-template-columns: repeat(auto-fit, 34px);
    -webkit-box-pack: space-evenly;
    -ms-flex-pack: space-evenly;
    justify-content: space-evenly;
    text-align: center;
  }
}

.SidebarMenu__CurrencySelector + .SidebarMenu__Social {
  border-left: 1px solid $navigation-border-color;
}

.SidebarMenu .Drawer__Content::before,
.SidebarMenu .Drawer__Footer::before {
  position: absolute;
  content: '';
  width: 100%;
  pointer-events: none;
  z-index: 1;
}

.SidebarMenu .Drawer__Content::before {
  top: 0;
  height: 25px;
  background-image: -webkit-gradient(linear, left top, left bottom, from($navigation-background), color-stop(40%, rgba($navigation-background, 0.6)), to(rgba($navigation-background, 0)));
  background-image: linear-gradient($navigation-background, rgba($navigation-background, 0.6) 40%, rgba($navigation-background, 0));
}

.SidebarMenu .Drawer__Footer::before {
  bottom: 100%;
  height: 30px;
  background-image: -webkit-gradient(linear, left top, left bottom, from(rgba($navigation-background, 0)), color-stop(40%, rgba($navigation-background, 0.6)), to($navigation-background));
  background-image: linear-gradient(rgba($navigation-background, 0), rgba($navigation-background, 0.6) 40%, $navigation-background);
}

@include av-mq('lap-and-up') {
  .SidebarMenu .Drawer__Content::before {
    height: 40px;
  }

  .SidebarMenu .Drawer__Main {
    padding-top: 26px;
  }

  .SidebarMenu .Drawer__Main::after {
    height: 60px; /* same here, Safari has some issues with adding padding-bottom :( */
  }

  .SidebarMenu .Drawer__Footer::before {
    height: 70px;
  }
}
/**
 * ----------------------------------------------------------------------------
 * Slideshow
 * ----------------------------------------------------------------------------
 */

.shopify-section--slideshow {
  position: relative;
}

.Slideshow--fullscreen {
  height: 100vh;
}

@supports (--css: variables) {
  .js .Slideshow--fullscreen {
    height: calc(var(--window-height) - (var(--header-height) * var(--header-is-not-transparent, 0)) - var(--announcement-bar-height, 0px));
  }
}

/* Slideshow transition are handled in JavaScript, so while we use Flickity, we need to disable any transition */

.js .Slideshow__Carousel {
  .Slideshow__Slide {
    -webkit-transition: none;
    transition: none;
  }

  .Slideshow__Slide.is-selected {
    visibility: hidden;
  }
}

.Slideshow__ImageContainer {
  height: 100%;
}

.Slideshow--fullscreen .Slideshow__Image {
  display: block;
  height: 100%;
  width: 100%;
  -o-object-fit: cover;
  object-fit: cover;
  -o-object-position: center;
  object-position: center;
  font-family: 'object-fit: cover; object-position: center;'; /* polyfill for IE */
}

.Slideshow__Image {
  z-index: 0;
}

@supports ((-o-object-fit: cover) or (object-fit: cover)) {
  .js .Slideshow__Image {
    opacity: 0;
  }
}

.Slideshow__Content {
  position: absolute;
  padding: 0 24px;
  width: 100%;
  left: 50%;
  top: 50%;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  text-align: center;
}

.js .Slideshow__Content .SectionHeader {
  opacity: 0;
}

.Slideshow__ScrollButton {
  position: absolute;
  left: calc(50% - 25px);
  bottom: -25px;
}

.Slideshow__Carousel--withScrollButton {
  margin-bottom: 25px;
}

.Slideshow--fullscreen {
  .Slideshow__ScrollButton {
    bottom: 10px;
  }

  .Slideshow__Carousel--withScrollButton {
    max-height: calc(100% - 35px);
    margin-bottom: 0;
  }
}

@include av-mq('lap-and-up') {
  .Slideshow__Content {
    padding: 0 70px;
  }

  .Slideshow__Content--middleLeft,
  .Slideshow__Content--bottomLeft {
    text-align: left;

    .ButtonGroup {
      -webkit-box-pack: start;
      -ms-flex-pack: start;
      justify-content: flex-start;
    }
  }

  .Slideshow__Content--bottomLeft,
  .Slideshow__Content--bottomCenter {
    top: auto;
    bottom: 70px;
    left: 0;
    -webkit-transform: none;
    transform: none;
  }
}
/**
 * For now testimonials are only used on home page but may be expanded
 */

@-webkit-keyframes testimonialOpening {
  from {
    visibility: hidden;
    opacity: 0;
    -webkit-transform: translateY(15px);
    transform: translateY(15px);
  }

  to {
    visibility: visible;
    opacity: 1;
    -webkit-transform: translateY(0);
    transform: translateY(0);
  }
}

@keyframes testimonialOpening {
  from {
    visibility: hidden;
    opacity: 0;
    -webkit-transform: translateY(15px);
    transform: translateY(15px);
  }

  to {
    visibility: visible;
    opacity: 1;
    -webkit-transform: translateY(0);
    transform: translateY(0);
  }
}

@-webkit-keyframes testimonialClosing {
  from {
    visibility: visible;
    opacity: 1;
    -webkit-transform: translateY(0);
    transform: translateY(0);
  }

  to {
    visibility: visible;
    opacity: 0;
    -webkit-transform: translateY(-15px);
    transform: translateY(-15px);
  }
}

@keyframes testimonialClosing {
  from {
    visibility: visible;
    opacity: 1;
    -webkit-transform: translateY(0);
    transform: translateY(0);
  }

  to {
    visibility: visible;
    opacity: 0;
    -webkit-transform: translateY(-15px);
    transform: translateY(-15px);
  }
}

.Testimonial {
  text-align: center;
  font-size: to-size(18px);
}

.Testimonial__Logo {
  margin-top: 54px;
}

.js .TestimonialList {
  opacity: 0;
  -webkit-transition: opacity 0s linear 0.5s;
  transition: opacity 0s linear 0.5s;

  &.flickity-enabled {
    opacity: 1;
  }

  .flickity-viewport {
    overflow: visible;
  }

  .flickity-page-dots {
    position: relative;
    margin-top: 60px;
  }

  .Testimonial {
    opacity: 0;
    visibility: hidden;
    -webkit-animation: testimonialClosing 0.4s cubic-bezier(0.55, 0.055, 0.675, 0.19) forwards;
    animation: testimonialClosing 0.4s cubic-bezier(0.55, 0.055, 0.675, 0.19) forwards;
  }

  .Testimonial.is-selected {
    opacity: 0;
    visibility: hidden;
    -webkit-animation: testimonialOpening 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94) 0.8s forwards;
    animation: testimonialOpening 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94) 0.8s forwards;
  }
}

@include av-mq('phone') {
  .Testimonial__Logo {
    max-width: 110px;
  }
}

@include av-mq('tablet-and-up') {
  .Testimonial {
    font-size: to-size(20px);
  }

  .Testimonial__Content {
    max-width: 550px;
    margin: 0 auto;
  }

  .Testimonial__Logo,
  .TestimonialNav__Item {
    max-width: 150px;
  }
}

@include av-mq('lap-and-up') {
  .TestimonialList--withNav .flickity-page-dots {
    display: none;
  }

  .TestimonialNav {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    justify-content: center;
    margin-top: 70px;
  }

  .TestimonialNav__Item {
    margin: 0 25px;
    cursor: pointer;
    opacity: 0.25;
    -webkit-transition: opacity 0.2s ease-in-out;
    transition: opacity 0.2s ease-in-out;
    will-change: opacity;
  }

  .TestimonialNav__Item.is-selected {
    opacity: 1;
  }
}

@include av-mq('desk') {
  .TestimonialNav__Item {
    margin: 0 45px;
  }
}
/**
 * ----------------------------------------------------------------------------
 * For now timeline are only used on home page but may be expanded
 * ----------------------------------------------------------------------------
 */

.Timeline {
  -webkit-box-shadow: 0 -2px 10px rgba(#363636, 0.2);
  box-shadow: 0 -2px 10px rgba(#363636, 0.2);
}

.Timeline__ListItem {
  position: relative;
  height: 540px;
  text-shadow: 0 1px rgba(#000000, 0.5);
}

.Timeline__Item {
  position: absolute;
  top: 0;
  left: 0;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: start;
  -ms-flex-align: start;
  align-items: flex-start;
  width: 100%;
  height: 100%;
  opacity: 0;
  background: rgba(#363636, 0.2);
  pointer-events: none;
  -webkit-transition: opacity 0.5s ease-in-out;
  transition: opacity 0.5s ease-in-out;
}

.Timeline__ImageWrapper {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.Timeline__Image {
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  -webkit-transform: translateX(-50px) scale(1.1);
  transform: translateX(-50px) scale(1.1);
  -webkit-transform-origin: left;
  transform-origin: left;
  -webkit-transition: -webkit-transform 0.5s cubic-bezier(0.645, 0.045, 0.355, 1);
  transition: -webkit-transform 0.5s cubic-bezier(0.645, 0.045, 0.355, 1);
  transition: transform 0.5s cubic-bezier(0.645, 0.045, 0.355, 1);
  transition: transform 0.5s cubic-bezier(0.645, 0.045, 0.355, 1), -webkit-transform 0.5s cubic-bezier(0.645, 0.045, 0.355, 1);
}

.Timeline__Inner {
  position: relative;
  padding: 80px 14px 40px 14px;
  max-height: 100%;
  overflow: auto;
  -webkit-overflow-scrolling: touch;
}

.Timeline__Header > * {
  opacity: 0;
  -webkit-transform: translateY(30px);
  transform: translateY(30px);
  -webkit-transition: opacity 0.5s cubic-bezier(0.215, 0.61, 0.355, 1), -webkit-transform 1s cubic-bezier(0.215, 0.61, 0.355, 1) 0.5s;
  transition: opacity 0.5s cubic-bezier(0.215, 0.61, 0.355, 1), -webkit-transform 1s cubic-bezier(0.215, 0.61, 0.355, 1) 0.5s;
  transition: opacity 0.5s cubic-bezier(0.215, 0.61, 0.355, 1), transform 1s cubic-bezier(0.215, 0.61, 0.355, 1) 0.5s;
  transition: opacity 0.5s cubic-bezier(0.215, 0.61, 0.355, 1), transform 1s cubic-bezier(0.215, 0.61, 0.355, 1) 0.5s, -webkit-transform 1s cubic-bezier(0.215, 0.61, 0.355, 1) 0.5s;
}

.Timeline__Header > .SectionHeader__Description {
  -webkit-transform: translateY(50px);
  transform: translateY(50px);
}

.Timeline__Item.is-selected {
  opacity: 1;
  pointer-events: auto;

  .Timeline__Image {
    -webkit-transform: translateX(0) scale(1.1);
    transform: translateX(0) scale(1.1);
  }

  .Timeline__Header > * {
    opacity: 1;
    -webkit-transition-delay: 0.5s;
    transition-delay: 0.5s;
    -webkit-transform: translateY(0);
    transform: translateY(0);
  }
}

@include av-mq('phone') {
  .shopify-section--timeline {
    border-top: none !important;
  }

  .shopify-section--timeline .Section {
    padding-top: 0 !important;
    padding-bottom: 0 !important;
  }

  .shopify-section--timeline .Container {
    padding-left: 0;
    padding-right: 0;
  }

  .Timeline__Header .Heading,
  .Timeline__Header .Rte a {
    color: inherit;
  }

  .Timeline__Header .SectionHeader__Description {
    margin: 34px 30px 0 30px;
  }
}

@include av-mq('tablet-and-up') {
  .Timeline__ListItem {
    max-width: 1230px;
    margin: 0 auto;
    height: 400px;
    text-shadow: none;
  }

  .Timeline__Item {
    -webkit-box-align: end;
    -ms-flex-align: end;
    align-items: flex-end;
    background-color: $light-background;
  }

  .Timeline__ImageWrapper,
  .Timeline__Inner {
    -webkit-box-flex: 0;
    -ms-flex: none;
    flex: none;
    width: 50%;
  }

  .Timeline__ImageWrapper {
    position: relative;
    height: 100%;

    &::after {
      display: none; /* Remove any contrast that may have been added to image */
    }
  }

  .Timeline__Image {
    -webkit-transform: translateX(-60px) scale(1.1);
    transform: translateX(-60px) scale(1.1);
  }

  .Timeline__Inner {
    padding: 34px 40px;
    color: $text-color;
  }

  .Timeline__Header {
    text-align: left;
  }
}

@include av-mq('lap-and-up') {
  .Timeline__ListItem {
    height: 515px;
  }

  .Timeline__Inner {
    padding: 54px 60px;
  }
}

/**
 * ----------------------------------------------------------------------------
 * Timeline nav
 * ----------------------------------------------------------------------------
 */

.Timeline__Nav {
  position: relative;
  font-size: to-size(11px);
  font-family: $heading-font-family;
  font-weight: $heading-font-weight;
  font-style: $heading-font-style;
  letter-spacing: 0.2em;
  color: $text-color-light;
  background: $light-background;
}

.Timeline__NavWrapper {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: start;
  -ms-flex-pack: start;
  justify-content: flex-start;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  white-space: nowrap;
  -webkit-overflow-scrolling: touch;
  overflow: auto;
}

.Timeline__NavWrapper--center {
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
}

.Timeline__NavItem {
  position: relative;
  padding: 30px 20px;
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  letter-spacing: inherit;
  vertical-align: text-bottom;
  -webkit-transition: all 0.25s ease-in-out;
  transition: all 0.25s ease-in-out;

  &::after {
    position: absolute;
    content: '';
    bottom: 0;
    left: 20px;
    height: 3px;
    width: calc(100% - 40px - 0.2em);
    opacity: 0;
    background: $text-color;
    -webkit-transform: scale(0, 1);
    transform: scale(0, 1);
    -webkit-transform-origin: left center;
    transform-origin: left center;
    -webkit-transition: opacity 0.3s, -webkit-transform 0.3s;
    transition: opacity 0.3s, -webkit-transform 0.3s;
    transition: opacity 0.3s, transform 0.3s;
    transition: opacity 0.3s, transform 0.3s, -webkit-transform 0.3s;
  }
}

.Timeline__NavItem.is-selected {
  font-size: to-size(18px);
  color: $text-color;

  &::after {
    opacity: 1;
    -webkit-transform: scale(1, 1);
    transform: scale(1, 1);
  }
}

.Timeline__NavLabel {
  display: block;
  line-height: 0;
}

@include av-mq('tablet-and-up') {
  .Timeline {
    -webkit-box-shadow: none;
    box-shadow: none;
  }

  .Timeline__Nav {
    margin-top: 40px;
    background: none;
    font-size: to-size(12px);
  }

  .Timeline__NavWrapper {
    display: block;
    text-align: center;
  }

  .Timeline__NavItem {
    padding-top: 20px;
    padding-bottom: 20px;
  }
}

@include av-mq('desk') {
  .Timeline__Nav {
    margin-top: 65px;
  }
}
