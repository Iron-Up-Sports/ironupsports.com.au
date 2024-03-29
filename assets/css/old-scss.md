---
---

// variables
// start content
@charset "utf-8";
$body-font: "Roboto", Helvetica, Arial, sans-serif;
$heading-font: "Roboto", Helvetica, Arial, sans-serif;
$button-font: "Roboto", Helvetica, Arial, sans-serif;

$base-font-size: 16px;

$base-spacing: 32px;

// lassio-colours
$lurple: #1924FF;
$leal: #19FFE7;
$lark-orange: #FF590D;

$soaring-eagle: #95afc0;
$pure-apple: #6ab04c;
$wizard-gray: #535c68;
$turbo: #f9ca24;
$blurple: #4834d4;
$pink-glamour: #ff7979;
$june-bud: #badc58;
$greeland-green: #22a6b3;
$beekeeper: #f6e58d;
$middle-blue: #7ed6df;
$coastal-breeze: #dff9fb;
$hint-of-ice-pack: #c7ecee;
$middle-blue: #7ed6df;
$kiwi-brown: #c1684e;
$iron-red: #cb1324;

//custom colours
$pink-glamour-25: #ff7979;

// colours
$text-color: #888;
$heading-color: #333;
$link-color: $iron-red;
$footer-color: none;
$timeline-line-color: #ffac86;
$timeline-box-color: #f5f4f3;
$timeline-dot-color: $lark-orange;
$logo-size: calc($base-spacing * 2);

// breakpoints
@mixin for-phone-only {
  @media (max-width: 599px) { @content; }
}
@mixin for-tablet-portrait-up {
  @media (min-width: 600px) { @content; }
}
@mixin for-tablet-landscape-up {
  @media (min-width: 900px) { @content; }
}
@mixin for-desktop-up {
  @media (min-width: 1200px) { @content; }
}
@mixin for-big-desktop-up {
  @media (min-width: 1800px) { @content; }
}

/* html elements */

* {
  box-sizing: border-box;
  color: $text-color;
  margin: 0;
  padding: 0;
}

%clearfix {

    &:after {
        content: "";
        display: table;
        clear: both;
    }
}

html, body {
   height: 100%;
 }

body {
  font-size: $base-font-size;
  display: flex;
  flex-direction: column;
  font-family: $body-font;
  @include for-desktop-up {
    font-size: $base-font-size * 1.5;
  }
}

.row {
  display: flex;
  width: 100%; /* Make the row fill the width of the window */
  /*background-color: #222;*/

  &.row-background {
    background-color: $beekeeper; /* Override background color if needed */
    background-image: url('../images/Header/5.png');
    background-size: cover; /* Adjust background size as needed */
    background-repeat: no-repeat; /* Prevent background image from repeating */
    background-position: center; /* Center the background image */
  }
}

.content-wrapper {
  width: 90%; /* Default width for the content */
  margin: 0 auto; /* Center the content horizontally */

  @media screen and (min-width: 768px) {
    width: 960px; /* Adjust width for tablets and larger screens */
  }

  @media screen and (min-width: 1200px) {
    width: 1140px; /* Adjust width for desktops and larger screens */
  }
}

/* Ensure columns expand evenly */
.columns {
  display: flex;
  flex-direction: row;
  width: 100%;
  /*background-color: #badc58;*/
}

.column {
  flex-grow: 1; /* Ensure columns expand evenly */
  flex-basis: 0;
  /* padding: calc($base-spacing / 2); Add padding to columns */
  box-sizing: border-box; /* Ensure padding is included in the width */
  margin-left: calc($base-spacing / 2); /* Add margin between columns */
  margin-right: calc($base-spacing / 2);

  &:first-child {
    margin-left: 0; /* Remove margin from the first column */
  }

  &:last-child {
    margin-right: 0; /* Remove margin from the last column */
  }

  &.background-img {
    background-color: $beekeeper; /* Override background color if needed */
    background-image: url('../images/Header/5.png');
    background-size: cover; /* Adjust background size as needed */
    background-repeat: no-repeat; /* Prevent background image from repeating */
    background-position: center; /* Center the background image */
  }
}



/* Example styling for individual columns */
/*.column:nth-child(1) {
  background: orange;
}

.column:nth-child(2) {
  background: teal;
}

.column:nth-child(3) {
  background: blue;
}*/

/* Define specific widths for different column classes */
.half {
  flex-basis: 50%;
}

.quarter {
  flex-basis: 25%;
}

.third {
  flex-basis: 33%;
}

.two-thirds {
  flex-basis: 66%;
}

.remove-padding {
  padding: 0;
}

.add-padding {
  padding: $base-spacing 0;
}

.row.hero {
  margin-top: $base-spacing * 2;
}


/* controls column layout */
/* Adjust width for different screen sizes */
@include for-phone-only {
  .column {
    width: 100%; /* Set columns to 100% width for phones */
  }
}





// new cols using flex
.col-4, .col-3 {
  flex: 1; // Allow columns to grow within the flex container
  padding-right: $base-spacing;

  @include for-phone-only {
    width: 100%; // For phones, take up the full width
    margin-bottom: calc($base-spacing / 2);
  }

  @include for-tablet-portrait-up {
    width: 50%; // For tablets, take up 50% width
  }

  @include for-tablet-landscape-up {
    width: 33.33%; // For landscape tablets, take up 33.33% width
  }
}


// dark mode
html.dark body {
  background-color: #333;
  h1, h3, h4 {
    color: #fff;
  }
}

h1, h2, h3, h4, p, ol, ul {
  margin-bottom: calc($base-spacing / 2);

  @include for-desktop-up {
    margin-bottom: calc($base-spacing / 2 * 1.5);
  }
}
h1, h2, h3, h4 {
  font-family: $heading-font;
  color: $heading-color;
  letter-spacing: -1px;
  line-height: 100%;
  font-weight: 500;

  a {font-family: $heading-font !important}
}
h1 {
  font-size: $base-font-size * 2;
  margin-bottom: calc($base-spacing / 2);

  @include for-desktop-up {
    font-size: $base-font-size * 3;
  }
}
h2 {
  color: $iron-red;
  font-size: $base-font-size * 1.25;
  margin-top: $base-spacing;
  margin-bottom: calc($base-spacing / 2);

  @include for-desktop-up {
    font-size: $base-font-size * 1.875;
    margin-top: $base-spacing * 1.5;
  }
}
h3 {
  font-size: $base-font-size * 1.125;

  @include for-desktop-up {
    font-size: $base-font-size * 1.5;
  }
}
h4 {
  font-size: $base-font-size;
}

a {
  color: $link-color;
  font-weight: 500;
  text-decoration: underline;
}
a:hover {
  color: #ffffff;
  background: $link-color;
  text-decoration: none;

}
img {
  max-width: 100%;
  vertical-align: middle;
  }
ul, ol {
  margin-top: 0;
  margin-bottom: 0;
  margin-left: $base-spacing;
  padding-top: 0;
  padding-bottom: 0;

}
blockquote {
  margin-top: $base-spacing * 2;
  padding: 0 $base-spacing;
  border-left: 8px solid $leal;
  font-style: italic;

  p, strong {
    color: $text-color;
  }
  img {
    max-width: 2em;
  }

}
nav {
  margin-top: $base-spacing * 3;
  padding-bottom: $base-spacing;
  line-height: $base-spacing;

  a {
    margin-right: calc($base-spacing / 2);
    white-space: nowrap;
  }
}

form {
  max-width: 60%;
  margin-top: 30px;
  margin-bottom: calc($base-spacing / 2);

  @include for-phone-only {
    max-width: 100%;
 }
}

input {
    width: 100%;
    color: $text-color;
    font-size: $base-font-size;

    @include for-desktop-up {
      font-size: $base-font-size * 1.5;
    }
}
button {
  font-family: $button-font;
}
.button {
  background-color: $link-color;
  border: none;
  color: white;
  padding: $base-spacing * 0.5;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-family: $button-font;
  font-size: 100%;
  line-height: 1rem;
  font-weight: 500;
  border: 2px solid $link-color;
}

.button {
  -webkit-transition-duration: 0.4s; /* Safari */
  transition-duration: 0.4s;
}

.button:hover {
  background-color: white;
  border: 2px solid $link-color;
  color: $link-color;
  cursor: pointer;
}

ms-style.ms-style-override {
  font-family: $body-font;
  font-size: $base-font-size;
}

input[type=text],
input[type=email] {
//  font-size: $base-font-size;
  margin-bottom: calc($base-spacing / 2);
  padding: 5px;
  box-sizing: border-box;
}

// Define mixin for 'appearance' property
@mixin appearance($value) {
  -webkit-appearance: $value;
  -moz-appearance: $value;
  appearance: $value;
}

input[type=button],
input[type=submit],
input[type=reset] {
    background-color: $link-color;
    border: none;
    color: white;
    padding: 15px 30px;
    text-decoration: none;
    cursor: pointer;
    width: 100%;
    font-weight: 700;
    font-family: $button-font;

    // Apply mixin for 'appearance' property
    @include appearance(none);

    @include for-phone-only {
      max-width: 100%;
   }
}

input[type=button]:hover {
  background-color: $middle-blue;
}

footer {
  background-color: $footer-color;
  font-size: $base-font-size * 0.8;
  padding-top: $base-spacing * 2;
  padding-bottom: $base-spacing;
  line-height: $base-spacing;
  clear: both;

  @include for-desktop-up {
    font-size: $base-font-size * 1.5 * 0.8;
  }
}

// custom styles!!!
.rapper {
  margin-left: auto;
  margin-right: auto;
  margin-top: $base-spacing * 3;
  width: 100%;
  padding-left: $base-spacing;
  padding-right: $base-spacing;
  height: 100%;
  @extend %clearfix;

  @include for-tablet-landscape-up {
    max-width: 1080px;
    padding-left: $base-spacing * 1.5;
    padding-right: $base-spacing * 1.5;
  }
}

.product-logo {
  max-width: calc($base-spacing * 2);
  margin-bottom: $base-spacing;
  margin-right: calc($base-spacing / 2); /* Add margin between the logo and other content */

  img {
    border-radius: 8px;
    width: 80px;
  }

  @include for-phone-only {
    max-width: $base-spacing * 1.5;
    margin-bottom: calc($base-spacing / 2);
  }
}


.feature-icon {
  margin-bottom: calc($base-spacing / 2);
  margin-top: calc($base-spacing / 2);

  img {
    border-radius: 8px;
    width: $base-spacing * 1.5
  }

  @include for-phone-only {
    max-width: $base-spacing * 1.5;
  }
}

.home-page > .feature-icon {
  margin-top: calc($base-spacing / 4);
}

.bunch {
  float: left;
  padding-right: calc($base-spacing / 2);
}


.first {
  padding-right: $base-spacing;
  background: yellow;
}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}

.hero {
  margin-bottom: $base-spacing * 2;
  //text-align: center;
}

.hero-img {
  //margin-top: $base-spacing;
  width: 100%;
  float: left;
  width: 25%;
  margin: 0;
  padding: $base-spacing * 0.5;

  @include for-phone-only {
    text-align: center;
    width: 100%;

  }

  img {
    max-width: 100%;

    @include for-phone-only {
      //float: none;
    }
  }
}

// logo
.logo-button {
  font-size: $base-font-size * 2;
  margin-left: $base-spacing;
  margin-top: $base-spacing * .875;

  @include for-phone-only {
    margin-top: $base-spacing * 1.175;
  }

  @include for-tablet-landscape-up {
      margin-left: $base-spacing;
  }

  @include for-desktop-up {
    font-size: $base-font-size * 3;
    margin-left: calc($base-spacing * 1.5);
  }

  a:hover{
    background: none;
  }
/*controls logo size*/
  img {
    max-height: $logo-size;

    @include for-desktop-up {
      max-height: calc($logo-size * 1);
    }
  }
}

.hide {display: none;}

.highlight {background-color: rgba(246,229,141,0.5);}

.blog-post {
  margin-bottom: $base-spacing * 4;
}

.page-controls {
  a:hover {
    background: none;
  }
}

.prev-next-button:nth-child(2) {
  margin-left: $base-spacing;
}

.post-meta-data {
  color: $soaring-eagle;
  font-size: $base-font-size * 0.8;

  @include for-desktop-up {
    font-size: $base-font-size * 1.5 * 0.8;
  }
}

.emoji-list {
  margin-bottom: $base-spacing;

  ul {
    margin-left: 0;
  }
  li {
    list-style: none;
    line-height: $base-spacing * 1.25;

    @include for-desktop-up {
      line-height: $base-spacing * 1.5 * 1.25;
    }
  }
  i {
    margin-right: calc($base-spacing / 4);
  }
}

.profile-pic {
  // border-radius: 100%;
  max-width: 100%;

  @include for-desktop-up {
  }
}

.content {
  ul {
    margin-bottom: calc($base-spacing / 2);

    @include for-desktop-up {
      margin-bottom: $base-spacing;
    }
  }
}

strong {
  font-weight: 500;
}

.dot {
  height: 25px;
  width: 25px;
  border-radius: 50%;
  display: inline-block;
  background-color: $leal;
}

// layout

// flex
.flex-container {
  display: flex;
  flex-wrap: nowrap;
  margin-bottom: 60px;
}

.flex-container > div {
  width: 50%;
}

// timeline

* {
  box-sizing: border-box;
}

/* The actual timeline (the vertical ruler) */
.timeline {
  position: relative;
  max-width: 1200px;
  margin: 0 auto;
}

/* The actual timeline (the vertical ruler) */
.timeline::after {
  content: '';
  position: absolute;
  width: 6px;
  background-color: $timeline-line-color;
  top: 0;
  bottom: 0;
  left: 50%;
  margin-left: -3px;
}

/* Container around content */
.container {
  padding: 0 40px 48px 40px;
  position: relative;
  background-color: inherit;
  width: 50%;
}

/* The circles on the timeline */
.container::after {
  content: '';
  position: absolute;
  width: 25px;
  height: 25px;
  right: -17px;
  background-color: $timeline-dot-color;
  border: 4px solid $timeline-dot-color;
  top: 15px;
  border-radius: 50%;
  z-index: 1;
}

/* Place the container to the left */
.left {
  left: 0;
}

/* Place the container to the right */
.right {
  left: 50%;
}

/* Add arrows to the left container (pointing right) */
.left::before {
  content: " ";
  height: 0;
  position: absolute;
  top: 22px;
  width: 0;
  z-index: 1;
  right: 30px;
  border: medium solid $timeline-box-color;
  border-width: 10px 0 10px 10px;
  border-color: transparent transparent transparent $timeline-box-color;
}

/* Add arrows to the right container (pointing left) */
.right::before {
  content: " ";
  height: 0;
  position: absolute;
  top: 22px;
  width: 0;
  z-index: 1;
  left: 30px;
  border: medium solid $timeline-box-color;
  border-width: 10px 10px 10px 0;
  border-color: transparent $timeline-box-color transparent transparent;
}

/* Fix the circle for containers on the right side */
.right::after {
  left: -16px;
}

/* The actual content */
.timeline-content {
  padding: 20px 30px;
  background-color: $timeline-box-color;
  position: relative;
  /*border-radius: 6px;*/
}

/* Media queries - Responsive timeline on screens less than 600px wide */
@media screen and (max-width: 600px) {
  /* Place the timelime to the left */
  .timeline::after {
  left: 31px;
  }

  /* Full-width containers */
  .container {
  width: 100%;
  padding-left: 70px;
  padding-right: 25px;
  }

  /* Make sure that all arrows are pointing leftwards */
  .container::before {
  left: 60px;
  border: medium solid $timeline-box-color;
  border-width: 10px 10px 10px 0;
  border-color: transparent $timeline-box-color transparent transparent;
  }

  /* Make sure all circles are at the same spot */
  .left::after, .right::after {
  left: 15px;
  }

  /* Make all right containers behave like the left ones */
  .right {
  left: 0%;
  }
}

/* full-screen overlay nav */

body {
//  margin: 0;
//  width: 100vw;
//  height: 100vh;
  animation: bugfix infinite 1s;
  -webkit-animation: bugfix infinite 1s;
}

@keyframes bugfix { from {padding:0;} to {padding:0;}}
@-webkit-keyframes bugfix { from {padding:0;} to {padding:0;}}

#overlay-button {
  position: absolute;
  right: $base-spacing;
  top: $base-spacing;
  padding: 26px 11px;
  z-index: 5;
  cursor: pointer;
  user-select: none;
  span {
      height: 4px;
      width: 35px;
      border-radius: 2px;
      background-color: $link-color;
      position: relative;
      display: block;
      transition: all .2s ease-in-out;
      &:before {
        top: -10px;
        visibility: visible;
      }
      &:after {
        top: 10px;
      }
      &:before, &:after {
          height: 4px;
          width: 35px;
          border-radius: 2px;
          background-color: $link-color;
          position: absolute;
          content: "";
          transition: all .2s ease-in-out;
      }
    }
    &:hover span, &:hover span:before, &:hover span:after {
      background: $link-color; // colour of X
    }

    @include for-desktop-up {
      top: $base-spacing;
    }

}

input[type=checkbox] {
  display: none;
}

input[type=checkbox]:checked ~ #overlay {
  visibility: visible;
}

input[type=checkbox]:checked ~ #overlay-button {
  &:hover span, span{
    background: transparent;
  }
  span {
    &:before {
      transform: rotate(45deg) translate(7px, 7px);
      opacity: 1;
    }
    &:after {
      transform: rotate(-45deg) translate(7px, -7px);
    }
  }
}

#overlay {
  height: 100vh;
  width: 100vw;
  background: #fff;
  z-index: 2;
  visibility: hidden;
  position: fixed;
  top: 0;
  left: 0;
  &.active {
    visibility: visible;
  }
  ul {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    text-align: left;
    height: 100vh;
    padding-left: 0;
    list-style-type: none;
    li {
      padding: 1em;
    /*  a {
        color: white;
        text-decoration: none;
        font-size: 1.5em;
          &:hover {
          color: #333332;
        }
      }*/
    }
  }
}

// feature comparison table
table {
  border-collapse: collapse;
  border-spacing: 0;
  width: 100%;
  margin-bottom: $base-spacing * 2
  //border: 1px solid #ddd;
}

th {
  color: $heading-color;
  font-weight: normal;
}

th, td {
  text-align: center;
  padding: calc($base-spacing / 2);
}

th:first-child, td:first-child {
  text-align: left;
}

tr:nth-child(even) {
  background-color: #f2f2f2
}

.fa-check {
  color: green;
}

.fa-remove {
  color: red;
}

ul {
  margin-bottom: calc($base-spacing);
}

h6 {
  font-size: $base-spacing;
}

h5 {
  font-size: $base-font-size * 2;
}



// works?

// variables

// colours
$almost-black: #222222;
$beekeeper: #f6e58d;
$grey-4: #888888;
$iron-red: #cb1324;

// fonts
$body-font: "Roboto", Helvetica, Arial, sans-serif;
$heading-font: "Roboto", Helvetica, Arial, sans-serif;
$button-font: "Roboto", Helvetica, Arial, sans-serif;
$heading-color: $almost-black;
$text-color: $grey-4;
$link-color: $iron-red;

// sizes and spacing
$base-font-size: 16px;
$base-spacing: calc($base-font-size * 1.5);
$line-height-ratio: 1.5; // Adjust this ratio as needed

// breakpoints
@mixin for-phone-only {
  @media (max-width: 599px) { @content; }
}

@mixin for-tablet-portrait-up {
  @media (min-width: 600px) { @content; }
}

@mixin for-tablet-landscape-up {
  @media (min-width: 900px) { @content; }
}

@mixin for-desktop-up {
  @media (min-width: 1200px) { @content; }
}

/* html elements */

* {
  box-sizing: border-box;
  color: $text-color;
  margin: 0;
  padding: 0;
}

%clearfix {

    &:after {
        content: "";
        display: table;
        clear: both;
    }
}

html, body {
  height: 100%;
}

body {
 font-size: $base-font-size;
 display: flex;
 flex-direction: column;
 font-family: $body-font;
 @include for-desktop-up {
   font-size: $base-font-size * 1.5;
 }
}

//layout

.row {
  /*display: flex;*/
  width: 100%; /* Make the row fill the width of the window */

  &.row-background {
    background-color: $beekeeper; /* Override background color if needed */
    background-image: url('../images/Header/5.png');
    background-size: cover; /* Adjust background size as needed */
    background-repeat: no-repeat; /* Prevent background image from repeating */
    background-position: center; /* Center the background image */
  }
}

.content-wrapper {
  width: 90%; /* Default width for the content */
  margin: 0 auto; /* Center the content horizontally */

  @media screen and (min-width: 768px) {
    width: 960px; /* Adjust width for tablets and larger screens */
    background-color: aqua;
  }

  @media screen and (min-width: 1200px) {
    width: 1140px; /* Adjust width for desktops and larger screens */
  }
}

/* Ensure columns expand evenly */
.columns {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  width: 100%;
}

.column {
  flex-basis: 100%;
  /* padding: calc($base-spacing / 2); Add padding to columns */
  box-sizing: border-box; /* Ensure padding is included in the width */
  margin: 0 $base-spacing;

  &:first-child {
    margin-left: 0; /* Remove margin from the first column */
  }

  &:last-child {
    margin-right: 0; /* Remove margin from the last column */
  }

  &.background-img {
    background-color: $beekeeper; /* Override background color if needed */
    background-image: url('../images/Header/5.png');
    background-size: cover; /* Adjust background size as needed */
    background-repeat: no-repeat; /* Prevent background image from repeating */
    background-position: center; /* Center the background image */
  }
}

@media screen and (min-width: 768px) {
 
}


/* Define specific widths for different column classes */
/*.half {
  flex-basis: 50%;
}

.one-fourth {
  flex-basis: 25%;
}

.third {
  flex-basis: 33%;
}

.two-thirds {
  flex-basis: 66%;
}

.three-fourths {
  flex-basis: 75%;
}*/


.remove-padding {
  padding: 0;
}

.add-padding {
  padding: $base-spacing 0;
}

.row.hero {
  margin-top: $base-spacing * 2;
}

.icon-left {
  display: flex;  /*Use flexbox to align items */
}

.icon {
  flex-shrink: 0; /* Prevent the icon from shrinking */
  margin-right: calc($base-spacing / 2); /* Adjust margin between icon and content */
}

.content {
  flex-grow: 1; /* Allow content to grow to fill remaining space */
}

// typography
h1, h2, h3, h4, p, ol, ul {
  margin-bottom: calc($base-spacing / 2);

  @include for-desktop-up {
    margin-bottom: calc($base-spacing / 2 * 1.5);
  }
}
h1, h2, h3, h4 {
  font-family: $heading-font;
  color: $heading-color;
  letter-spacing: -1px;
  line-height: 100%;
  font-weight: 500;

  a {font-family: $heading-font !important}
}
h1 {
  font-size: $base-font-size * 2;
  line-height: 1.2;
  margin-bottom: calc($base-spacing / 2);

  @include for-desktop-up {
    font-size: $base-font-size * 3;
  }
}
h2 {
  color: $iron-red;
  font-size: $base-font-size * 1.25;
  line-height: 1.4;
  margin-bottom: calc($base-spacing / 2);

  @include for-desktop-up {
    font-size: $base-font-size * 1.875;
  }
}
h3 {
  font-size: $base-font-size * 1.125;

  @include for-desktop-up {
    font-size: $base-font-size * 1.5;
  }
}
h4 {
  font-size: $base-font-size;
}

a {
  color: $link-color;
  font-weight: 500;
  text-decoration: underline;
}
a:hover {
  color: #ffffff;
  background: $link-color;
  text-decoration: none;

}