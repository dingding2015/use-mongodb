<html><head><meta charset="utf-8"><style>body {
  max-width: 980px;
  border: 1px solid #ddd;
  outline: 1300px solid #fff;
  margin: 16px auto;
}

body .markdown-body
{
  padding: 45px;
}

@font-face {
  font-family: fontawesome-mini;
  src: url(data:font/woff;charset=utf-8;base64,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) format('woff');
}

@font-face {
  font-family: octicons-anchor;
  src: url(data:font/woff;charset=utf-8;base64,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) format('woff');
}

.markdown-body {
  font-family: sans-serif;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  color: #333333;
  overflow: hidden;
  font-family: "Helvetica Neue", Helvetica, "Segoe UI", Arial, freesans, sans-serif;
  font-size: 16px;
  line-height: 1.6;
  word-wrap: break-word;
}

.markdown-body a {
  background: transparent;
}

.markdown-body a:active,
.markdown-body a:hover {
  outline: 0;
}

.markdown-body b,
.markdown-body strong {
  font-weight: bold;
}

.markdown-body mark {
  background: #ff0;
  color: #000;
  font-style: italic;
  font-weight: bold;
}

.markdown-body sub,
.markdown-body sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}
.markdown-body sup {
  top: -0.5em;
}
.markdown-body sub {
  bottom: -0.25em;
}

.markdown-body h1 {
  font-size: 2em;
  margin: 0.67em 0;
}

.markdown-body img {
  border: 0;
}

.markdown-body hr {
  -moz-box-sizing: content-box;
  box-sizing: content-box;
  height: 0;
}

.markdown-body pre {
  overflow: auto;
}

.markdown-body code,
.markdown-body kbd,
.markdown-body pre,
.markdown-body samp {
  font-family: monospace, monospace;
  font-size: 1em;
}

.markdown-body input {
  color: inherit;
  font: inherit;
  margin: 0;
}

.markdown-body html input[disabled] {
  cursor: default;
}

.markdown-body input {
  line-height: normal;
}

.markdown-body input[type="checkbox"] {
  box-sizing: border-box;
  padding: 0;
}

.markdown-body table {
  border-collapse: collapse;
  border-spacing: 0;
}

.markdown-body td,
.markdown-body th {
  padding: 0;
}

.markdown-body .codehilitetable {
  border: 0;
  border-spacing: 0;
}

.markdown-body .codehilitetable tr {
  border: 0;
}

.markdown-body .codehilitetable pre,
.markdown-body .codehilitetable div.codehilite {
  margin: 0;
}

.markdown-body .linenos,
.markdown-body .code,
.markdown-body .codehilitetable td {
  border: 0;
  padding: 0;
}

.markdown-body td:not(.linenos) .linenodiv {
  padding: 0 !important;
}

.markdown-body .code {
  width: 100%;
}

.markdown-body .linenos div pre,
.markdown-body .linenodiv pre,
.markdown-body .linenodiv {
  border: 0;
  -webkit-border-radius: 0;
  -moz-border-radius: 0;
  border-radius: 0;
  -webkit-border-top-left-radius: 3px;
  -webkit-border-bottom-left-radius: 3px;
  -moz-border-radius-topleft: 3px;
  -moz-border-radius-bottomleft: 3px;
  border-top-left-radius: 3px;
  border-bottom-left-radius: 3px;
}

.markdown-body .code div pre,
.markdown-body .code div {
  border: 0;
  -webkit-border-radius: 0;
  -moz-border-radius: 0;
  border-radius: 0;
  -webkit-border-top-right-radius: 3px;
  -webkit-border-bottom-right-radius: 3px;
  -moz-border-radius-topright: 3px;
  -moz-border-radius-bottomright: 3px;
  border-top-right-radius: 3px;
  border-bottom-right-radius: 3px;
}

.markdown-body * {
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}

.markdown-body input {
  font: 13px Helvetica, arial, freesans, clean, sans-serif, "Segoe UI Emoji", "Segoe UI Symbol";
  line-height: 1.4;
}

.markdown-body a {
  color: #4183c4;
  text-decoration: none;
}

.markdown-body a:hover,
.markdown-body a:focus,
.markdown-body a:active {
  text-decoration: underline;
}

.markdown-body hr {
  height: 0;
  margin: 15px 0;
  overflow: hidden;
  background: transparent;
  border: 0;
  border-bottom: 1px solid #ddd;
}

.markdown-body hr:before,
.markdown-body hr:after {
  display: table;
  content: " ";
}

.markdown-body hr:after {
  clear: both;
}

.markdown-body h1,
.markdown-body h2,
.markdown-body h3,
.markdown-body h4,
.markdown-body h5,
.markdown-body h6 {
  margin-top: 15px;
  margin-bottom: 15px;
  line-height: 1.1;
}

.markdown-body h1 {
  font-size: 30px;
}

.markdown-body h2 {
  font-size: 21px;
}

.markdown-body h3 {
  font-size: 16px;
}

.markdown-body h4 {
  font-size: 14px;
}

.markdown-body h5 {
  font-size: 12px;
}

.markdown-body h6 {
  font-size: 11px;
}

.markdown-body blockquote {
  margin: 0;
}

.markdown-body ul,
.markdown-body ol {
  padding: 0;
  margin-top: 0;
  margin-bottom: 0;
}

.markdown-body ol ol,
.markdown-body ul ol {
  list-style-type: lower-roman;
}

.markdown-body ul ul ol,
.markdown-body ul ol ol,
.markdown-body ol ul ol,
.markdown-body ol ol ol {
  list-style-type: lower-alpha;
}

.markdown-body dd {
  margin-left: 0;
}

.markdown-body code,
.markdown-body pre,
.markdown-body samp {
  font-family: Consolas, "Liberation Mono", Menlo, Courier, monospace;
  font-size: 12px;
}

.markdown-body pre {
  margin-top: 0;
  margin-bottom: 0;
}

.markdown-body kbd {
  background-color: #e7e7e7;
  background-image: -moz-linear-gradient(#fefefe, #e7e7e7);
  background-image: -webkit-linear-gradient(#fefefe, #e7e7e7);
  background-image: linear-gradient(#fefefe, #e7e7e7);
  background-repeat: repeat-x;
  border-radius: 2px;
  border: 1px solid #cfcfcf;
  color: #000;
  padding: 3px 5px;
  line-height: 10px;
  font: 11px Consolas, "Liberation Mono", Menlo, Courier, monospace;
  display: inline-block;
}

.markdown-body>*:first-child {
  margin-top: 0 !important;
}

.markdown-body>*:last-child {
  margin-bottom: 0 !important;
}

.markdown-body .headeranchor-link {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  display: block;
  padding-right: 6px;
  padding-left: 30px;
  margin-left: -30px;
}

.markdown-body .headeranchor-link:focus {
  outline: none;
}

.markdown-body h1,
.markdown-body h2,
.markdown-body h3,
.markdown-body h4,
.markdown-body h5,
.markdown-body h6 {
  position: relative;
  margin-top: 1em;
  margin-bottom: 16px;
  font-weight: bold;
  line-height: 1.4;
}

.markdown-body h1 .headeranchor,
.markdown-body h2 .headeranchor,
.markdown-body h3 .headeranchor,
.markdown-body h4 .headeranchor,
.markdown-body h5 .headeranchor,
.markdown-body h6 .headeranchor {
  display: none;
  color: #000;
  vertical-align: middle;
}

.markdown-body h1:hover .headeranchor-link,
.markdown-body h2:hover .headeranchor-link,
.markdown-body h3:hover .headeranchor-link,
.markdown-body h4:hover .headeranchor-link,
.markdown-body h5:hover .headeranchor-link,
.markdown-body h6:hover .headeranchor-link {
  height: 1em;
  padding-left: 8px;
  margin-left: -30px;
  line-height: 1;
  text-decoration: none;
}

.markdown-body h1:hover .headeranchor-link .headeranchor,
.markdown-body h2:hover .headeranchor-link .headeranchor,
.markdown-body h3:hover .headeranchor-link .headeranchor,
.markdown-body h4:hover .headeranchor-link .headeranchor,
.markdown-body h5:hover .headeranchor-link .headeranchor,
.markdown-body h6:hover .headeranchor-link .headeranchor {
  display: inline-block;
}

.markdown-body h1 {
  padding-bottom: 0.3em;
  font-size: 2.25em;
  line-height: 1.2;
  border-bottom: 1px solid #eee;
}

.markdown-body h2 {
  padding-bottom: 0.3em;
  font-size: 1.75em;
  line-height: 1.225;
  border-bottom: 1px solid #eee;
}

.markdown-body h3 {
  font-size: 1.5em;
  line-height: 1.43;
}

.markdown-body h4 {
  font-size: 1.25em;
}

.markdown-body h5 {
  font-size: 1em;
}

.markdown-body h6 {
  font-size: 1em;
  color: #777;
}

.markdown-body p,
.markdown-body blockquote,
.markdown-body ul,
.markdown-body ol,
.markdown-body dl,
.markdown-body table,
.markdown-body pre,
.markdown-body .admonition {
  margin-top: 0;
  margin-bottom: 16px;
}

.markdown-body hr {
  height: 4px;
  padding: 0;
  margin: 16px 0;
  background-color: #e7e7e7;
  border: 0 none;
}

.markdown-body ul,
.markdown-body ol {
  padding-left: 2em;
}

.markdown-body ul ul,
.markdown-body ul ol,
.markdown-body ol ol,
.markdown-body ol ul {
  margin-top: 0;
  margin-bottom: 0;
}

.markdown-body li>p {
  margin-top: 16px;
}

.markdown-body dl {
  padding: 0;
}

.markdown-body dl dt {
  padding: 0;
  margin-top: 16px;
  font-size: 1em;
  font-style: italic;
  font-weight: bold;
}

.markdown-body dl dd {
  padding: 0 16px;
  margin-bottom: 16px;
}

.markdown-body blockquote {
  padding: 0 15px;
  color: #777;
  border-left: 4px solid #ddd;
}

.markdown-body blockquote>:first-child {
  margin-top: 0;
}

.markdown-body blockquote>:last-child {
  margin-bottom: 0;
}

.markdown-body table {
  display: block;
  width: 100%;
  overflow: auto;
  word-break: normal;
  word-break: keep-all;
}

.markdown-body table th {
  font-weight: bold;
}

.markdown-body table th,
.markdown-body table td {
  padding: 6px 13px;
  border: 1px solid #ddd;
}

.markdown-body table tr {
  background-color: #fff;
  border-top: 1px solid #ccc;
}

.markdown-body table tr:nth-child(2n) {
  background-color: #f8f8f8;
}

.markdown-body img {
  max-width: 100%;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}

.markdown-body code,
.markdown-body samp {
  padding: 0;
  padding-top: 0.2em;
  padding-bottom: 0.2em;
  margin: 0;
  font-size: 85%;
  background-color: rgba(0,0,0,0.04);
  border-radius: 3px;
}

.markdown-body code:before,
.markdown-body code:after {
  letter-spacing: -0.2em;
  content: "\00a0";
}

.markdown-body pre>code {
  padding: 0;
  margin: 0;
  font-size: 100%;
  word-break: normal;
  white-space: pre;
  background: transparent;
  border: 0;
}

.markdown-body .codehilite {
  margin-bottom: 16px;
}

.markdown-body .codehilite pre,
.markdown-body pre {
  padding: 16px;
  overflow: auto;
  font-size: 85%;
  line-height: 1.45;
  background-color: #f7f7f7;
  border-radius: 3px;
}

.markdown-body .codehilite pre {
  margin-bottom: 0;
  word-break: normal;
}

.markdown-body pre {
  word-wrap: normal;
}

.markdown-body pre code {
  display: inline;
  max-width: initial;
  padding: 0;
  margin: 0;
  overflow: initial;
  line-height: inherit;
  word-wrap: normal;
  background-color: transparent;
  border: 0;
}

.markdown-body pre code:before,
.markdown-body pre code:after {
  content: normal;
}

/* Admonition */
.markdown-body .admonition {
  -webkit-border-radius: 3px;
  -moz-border-radius: 3px;
  position: relative;
  border-radius: 3px;
  border: 1px solid #e0e0e0;
  border-left: 6px solid #333;
  padding: 10px 10px 10px 30px;
}

.markdown-body .admonition table {
  color: #333;
}

.markdown-body .admonition p {
  padding: 0;
}

.markdown-body .admonition-title {
  font-weight: bold;
  margin: 0;
}

.markdown-body .admonition>.admonition-title {
  color: #333;
}

.markdown-body .attention>.admonition-title {
  color: #a6d796;
}

.markdown-body .caution>.admonition-title {
  color: #d7a796;
}

.markdown-body .hint>.admonition-title {
  color: #96c6d7;
}

.markdown-body .danger>.admonition-title {
  color: #c25f77;
}

.markdown-body .question>.admonition-title {
  color: #96a6d7;
}

.markdown-body .note>.admonition-title {
  color: #d7c896;
}

.markdown-body .admonition:before,
.markdown-body .attention:before,
.markdown-body .caution:before,
.markdown-body .hint:before,
.markdown-body .danger:before,
.markdown-body .question:before,
.markdown-body .note:before {
  font: normal normal 16px fontawesome-mini;
  -moz-osx-font-smoothing: grayscale;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  line-height: 1.5;
  color: #333;
  position: absolute;
  left: 0;
  top: 0;
  padding-top: 10px;
  padding-left: 10px;
}

.markdown-body .admonition:before {
  content: "\f056\00a0";
  color: 333;
}

.markdown-body .attention:before {
  content: "\f058\00a0";
  color: #a6d796;
}

.markdown-body .caution:before {
  content: "\f06a\00a0";
  color: #d7a796;
}

.markdown-body .hint:before {
  content: "\f05a\00a0";
  color: #96c6d7;
}

.markdown-body .danger:before {
  content: "\f057\00a0";
  color: #c25f77;
}

.markdown-body .question:before {
  content: "\f059\00a0";
  color: #96a6d7;
}

.markdown-body .note:before {
  content: "\f040\00a0";
  color: #d7c896;
}

.markdown-body .admonition::after {
  content: normal;
}

.markdown-body .attention {
  border-left: 6px solid #a6d796;
}

.markdown-body .caution {
  border-left: 6px solid #d7a796;
}

.markdown-body .hint {
  border-left: 6px solid #96c6d7;
}

.markdown-body .danger {
  border-left: 6px solid #c25f77;
}

.markdown-body .question {
  border-left: 6px solid #96a6d7;
}

.markdown-body .note {
  border-left: 6px solid #d7c896;
}

.markdown-body .admonition>*:first-child {
  margin-top: 0 !important;
}

.markdown-body .admonition>*:last-child {
  margin-bottom: 0 !important;
}

/* progress bar*/
.markdown-body .progress {
  display: block;
  width: 300px;
  margin: 10px 0;
  height: 24px;
  -webkit-border-radius: 3px;
  -moz-border-radius: 3px;
  border-radius: 3px;
  background-color: #ededed;
  position: relative;
  box-shadow: inset -1px 1px 3px rgba(0, 0, 0, .1);
}

.markdown-body .progress-label {
  position: absolute;
  text-align: center;
  font-weight: bold;
  width: 100%; margin: 0;
  line-height: 24px;
  color: #333;
  text-shadow: 1px 1px 0 #fefefe, -1px -1px 0 #fefefe, -1px 1px 0 #fefefe, 1px -1px 0 #fefefe, 0 1px 0 #fefefe, 0 -1px 0 #fefefe, 1px 0 0 #fefefe, -1px 0 0 #fefefe, 1px 1px 2px #000;
  -webkit-font-smoothing: antialiased !important;
  white-space: nowrap;
  overflow: hidden;
}

.markdown-body .progress-bar {
  height: 24px;
  float: left;
  -webkit-border-radius: 3px;
  -moz-border-radius: 3px;
  border-radius: 3px;
  background-color: #96c6d7;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, .5), inset 0 -1px 0 rgba(0, 0, 0, .1);
  background-size: 30px 30px;
  background-image: -webkit-linear-gradient(
    135deg, rgba(255, 255, 255, .4) 27%,
    transparent 27%,
    transparent 52%, rgba(255, 255, 255, .4) 52%,
    rgba(255, 255, 255, .4) 77%,
    transparent 77%, transparent
  );
  background-image: -moz-linear-gradient(
    135deg,
    rgba(255, 255, 255, .4) 27%, transparent 27%,
    transparent 52%, rgba(255, 255, 255, .4) 52%,
    rgba(255, 255, 255, .4) 77%, transparent 77%,
    transparent
  );
  background-image: -ms-linear-gradient(
    135deg,
    rgba(255, 255, 255, .4) 27%, transparent 27%,
    transparent 52%, rgba(255, 255, 255, .4) 52%,
    rgba(255, 255, 255, .4) 77%, transparent 77%,
    transparent
  );
  background-image: -o-linear-gradient(
    135deg,
    rgba(255, 255, 255, .4) 27%, transparent 27%,
    transparent 52%, rgba(255, 255, 255, .4) 52%,
    rgba(255, 255, 255, .4) 77%, transparent 77%,
    transparent
  );
  background-image: linear-gradient(
    135deg,
    rgba(255, 255, 255, .4) 27%, transparent 27%,
    transparent 52%, rgba(255, 255, 255, .4) 52%,
    rgba(255, 255, 255, .4) 77%, transparent 77%,
    transparent
  );
}

.markdown-body .progress-100plus .progress-bar {
  background-color: #a6d796;
}

.markdown-body .progress-80plus .progress-bar {
  background-color: #c6d796;
}

.markdown-body .progress-60plus .progress-bar {
  background-color: #d7c896;
}

.markdown-body .progress-40plus .progress-bar {
  background-color: #d7a796;
}

.markdown-body .progress-20plus .progress-bar {
  background-color: #d796a6;
}

.markdown-body .progress-0plus .progress-bar {
  background-color: #c25f77;
}

.markdown-body .candystripe-animate .progress-bar{
  -webkit-animation: animate-stripes 3s linear infinite;
  -moz-animation: animate-stripes 3s linear infinite;
  animation: animate-stripes 3s linear infinite;
}

@-webkit-keyframes animate-stripes {
  0% {
    background-position: 0 0;
  }

  100% {
    background-position: 60px 0;
  }
}

@-moz-keyframes animate-stripes {
  0% {
    background-position: 0 0;
  }

  100% {
    background-position: 60px 0;
  }
}

@keyframes animate-stripes {
  0% {
    background-position: 0 0;
  }

  100% {
    background-position: 60px 0;
  }
}

.markdown-body .gloss .progress-bar {
  box-shadow:
    inset 0 4px 12px rgba(255, 255, 255, .7),
    inset 0 -12px 0 rgba(0, 0, 0, .05);
}

/* Multimarkdown Critic Blocks */
.markdown-body .critic_mark {
  background: #ff0;
}

.markdown-body .critic_delete {
  color: #c82829;
  text-decoration: line-through;
}

.markdown-body .critic_insert {
  color: #718c00 ;
  text-decoration: underline;
}

.markdown-body .critic_comment {
  color: #8e908c;
  font-style: italic;
}

.markdown-body .headeranchor {
  font: normal normal 16px octicons-anchor;
  line-height: 1;
  display: inline-block;
  text-decoration: none;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.headeranchor:before {
  content: '\f05c';
}

.markdown-body .task-list-item {
  list-style-type: none;
}

.markdown-body .task-list-item+.task-list-item {
  margin-top: 3px;
}

.markdown-body .task-list-item input {
  margin: 0 4px 0.25em -20px;
  vertical-align: middle;
}

/* Media */
@media only screen and (min-width: 480px) {
  .markdown-body {
    font-size:14px;
  }
}

@media only screen and (min-width: 768px) {
  .markdown-body {
    font-size:16px;
  }
}

@media print {
  .markdown-body * {
    background: transparent !important;
    color: black !important;
    filter:none !important;
    -ms-filter: none !important;
  }

  .markdown-body {
    font-size:12pt;
    max-width:100%;
    outline:none;
    border: 0;
  }

  .markdown-body a,
  .markdown-body a:visited {
    text-decoration: underline;
  }

  .markdown-body .headeranchor-link {
    display: none;
  }

  .markdown-body a[href]:after {
    content: " (" attr(href) ")";
  }

  .markdown-body abbr[title]:after {
    content: " (" attr(title) ")";
  }

  .markdown-body .ir a:after,
  .markdown-body a[href^="javascript:"]:after,
  .markdown-body a[href^="#"]:after {
    content: "";
  }

  .markdown-body pre {
    white-space: pre;
    white-space: pre-wrap;
    word-wrap: break-word;
  }

  .markdown-body pre,
  .markdown-body blockquote {
    border: 1px solid #999;
    padding-right: 1em;
    page-break-inside: avoid;
  }

  .markdown-body .progress,
  .markdown-body .progress-bar {
    -moz-box-shadow: none;
    -webkit-box-shadow: none;
    box-shadow: none;
  }

  .markdown-body .progress {
    border: 1px solid #ddd;
  }

  .markdown-body .progress-bar {
    height: 22px;
    border-right: 1px solid #ddd;
  }

  .markdown-body tr,
  .markdown-body img {
    page-break-inside: avoid;
  }

  .markdown-body img {
    max-width: 100% !important;
  }

  .markdown-body p,
  .markdown-body h2,
  .markdown-body h3 {
    orphans: 3;
    widows: 3;
  }

  .markdown-body h2,
  .markdown-body h3 {
    page-break-after: avoid;
  }
}
</style><title>a</title></head><body><article class="markdown-body"><h1 align="center">mongodb的使用</h1>

<div class="toc">
<ul>
<li><a href="#1-mongodb">1、 mongodb需要了解的一些概念</a></li>
<li><a href="#2-mongodb">2、 mongodb的连接</a></li>
<li><a href="#3mongodb-crud">3、mongodb CRUD 操作</a><ul>
<li><a href="#31-create-database">3.1 create database</a></li>
<li><a href="#32-drop-database">3.2 drop database</a></li>
<li><a href="#33-create-collection">3.3 create collection</a></li>
<li><a href="#34-drop-collection">3.4 drop collection</a></li>
<li><a href="#35-insert">3.5 insert</a></li>
<li><a href="#36-update">3.6 update</a></li>
<li><a href="#37-delete">3.7 delete</a></li>
<li><a href="#38-bulkwrite">3.8 bulkWrite</a></li>
<li><a href="#39-query">3.9 query</a></li>
</ul>
</li>
</ul>
</div>
<h2 id="1-mongodb"><a name="user-content-1-mongodb" href="#1-mongodb" class="headeranchor-link" aria-hidden="true"><span class="headeranchor"></span></a>1、 mongodb需要了解的一些概念</h2>
<ul>
<li>database 数据库 <br></li>
</ul>
<p>mongodb数据库存储在data目录中 <br><br />
  show dbs 显示所有的数据库 <br><br />
  use mydb 创建和切换数据库 <br></p>
<ul>
<li>collection 集合，数据库表，table  <br></li>
</ul>
<p>集合是mongodb文档组，存储在数据库中，没有固定的结构，可以插入不同格式和类型的数据。<br><br />
  capped collections 固定大小的集合，有很高的性能以及队列过期的特性，需要显式创建，指定集合的大小，提前分配存储空间。<br><br />
  向集合插入数据，如果集合不存在则会创建集合。<br></p>
<ul>
<li>document 数据记录行/文档，row <br></li>
</ul>
<p>文档是一组键/值对（BSON）,mongodb的文档不需要设置相同的字段，并且相同的字段不需要相同的数据类型。文档的键值对是有序的。mongodb区分类型和大小写。不能有重复的键。键是字符串，特殊情况可以使utf-8字符。<br><br />
  BSON is a binary serialization format used to store documents and make remote procedure calls in MongoDB. </p>
<ul>
<li>
<p>field 字段/域、column <br><br />
  mongodb支持的数据类型：<br />
  <pre><code><br />
  db.collection.insertOne() <br />
  </code></pre></p>
</li>
<li>
<p>index 索引 <br></p>
</li>
<li>
<p>primary key  主键，mongodb自动将_id字段设置为主键 <br></p>
</li>
</ul>
<h2 id="2-mongodb"><a name="user-content-2-mongodb" href="#2-mongodb" class="headeranchor-link" aria-hidden="true"><span class="headeranchor"></span></a>2、 mongodb的连接</h2>
<p>标准 URI 连接语法：<br />
    <pre><code><br />
    mongodb://[username:password@]host1[:port1][,host2[:port2],&hellip;[,hostN[:portN]]][/[database][?   options]]<br />
    </code></pre><br />
 mongodb:// 这是固定的格式，必须要指定。<br><br />
 username:password@ 可选项，如果设置，在连接数据库服务器之后， 驱动都会尝试登陆这个数据库.<br><br />
 host1:连接服务器 <br><br />
 portN:连接端口，默认27017 <br><br />
 database:默认数据库，不指定是test <br><br />
 option:连接选项 <br></p>
<h2 id="3mongodb-crud"><a name="user-content-3mongodb-crud" href="#3mongodb-crud" class="headeranchor-link" aria-hidden="true"><span class="headeranchor"></span></a>3、mongodb CRUD 操作</h2>
<h3 id="31-create-database"><a name="user-content-31-create-database" href="#31-create-database" class="headeranchor-link" aria-hidden="true"><span class="headeranchor"></span></a>3.1 create database</h3>
<pre><code>
rs0: PRIMARY> use mydb
switched to db mydb
rs0: PRIMARY> db
mydb
</code></pre>

<p>如果数据库存在则切换到数据库，如果不存在则创建。使用&rsquo;show dbs&rsquo;查看所有数据库，自己创建的数据库中必须存在document，才能显示。&rsquo;db&rsquo;，查看当前数据库。</p>
<h3 id="32-drop-database"><a name="user-content-32-drop-database" href="#32-drop-database" class="headeranchor-link" aria-hidden="true"><span class="headeranchor"></span></a>3.2 drop database</h3>
<pre><code>
rs0: PRIMARY> use mydb
switched to db mydb
rs0: PRIMARY> db
mydb
rs0: PRIMARY> db.dropDatabase()
{ "dropped" : "mydb", "ok" : 1 }
</code></pre>

<h3 id="33-create-collection"><a name="user-content-33-create-collection" href="#33-create-collection" class="headeranchor-link" aria-hidden="true"><span class="headeranchor"></span></a>3.3 create collection</h3>
<pre><code>
rs0: PRIMARY> use mydb
switched to db mydb
rs0: PRIMARY> db
mydb
rs0: PRIMARY> db.mycollection.insert({'name':'insert test','note':'insert learn'})
WriteResult({ "nInserted" : 1 })
rs0: PRIMARY> db.mycollection.find()
{ "_id" : ObjectId("5a4056a146245769d3e9e032"), "name" : "insert test", "note" : "insert learn" }
</code></pre>

<p>以上，&rsquo;_id&rsquo;没有指定，自动增加了，使用find()查询插入结果。<br />
插入数据，如果集合不存在则会创建集合。</p>
<h3 id="34-drop-collection"><a name="user-content-34-drop-collection" href="#34-drop-collection" class="headeranchor-link" aria-hidden="true"><span class="headeranchor"></span></a>3.4 drop collection</h3>
<pre><code>
rs0: PRIMARY> db
mydb
rs0: PRIMARY> show tables;
mycollection
rs0: PRIMARY> db.mycollection.drop()
true
rs0: PRIMARY> show tables;
rs0: PRIMARY> 
rs0: PRIMARY> 
</code></pre>

<p>&lsquo;show tables&rsquo;查看集合集。</p>
<h3 id="35-insert"><a name="user-content-35-insert" href="#35-insert" class="headeranchor-link" aria-hidden="true"><span class="headeranchor"></span></a>3.5 insert</h3>
<p>插入一条document到collection中，如果collection不存在，则创建collection。</p>
<ul>
<li>insert()插入单条记录</li>
</ul>
<pre><code>
rs0: PRIMARY> db.mycollection.insert({'name':'insert one','note':'insert learn'})
WriteResult({ "nInserted" : 1 })
</code></pre>

<ul>
<li>insert()插入多条记录</li>
</ul>
<pre><code>
rs0: PRIMARY> db.mycollection.insert([{'name':'delete one','note':'delete learn'},{'name':'delete two','note':'delete learn'},{'name':'delete three','note':'delete learn'}])
BulkWriteResult({
    "writeErrors" : [ ],
    "writeConcernErrors" : [ ],
    "nInserted" : 3,
    "nUpserted" : 0,
    "nMatched" : 0,
    "nModified" : 0,
    "nRemoved" : 0,
    "upserted" : [ ]
})
) 
</code></pre>

<ul>
<li>
<p>insertOne()插入单条记录<br />
<pre><code><br />
rs0: PRIMARY&gt; db.mycollection.insertOne({&lsquo;name&rsquo;:&rsquo;delete one&rsquo;,&rsquo;note&rsquo;:&rsquo;delete learn&rsquo;})<br />
{<br />
    &ldquo;acknowledged&rdquo; : true,<br />
    &ldquo;insertedId&rdquo; : ObjectId(&ldquo;5a406da246245769d3e9e048&rdquo;)<br />
}<br />
</code></pre></p>
</li>
<li>
<p>insertMany()插入多条记录<br />
<pre><code><br />
rs0: PRIMARY&gt; db.mycollection.insertMany([{&lsquo;name&rsquo;:&rsquo;delete one&rsquo;,&rsquo;note&rsquo;:&rsquo;delete learn&rsquo;},{&lsquo;name&rsquo;:&rsquo;delete two&rsquo;,&rsquo;note&rsquo;:&rsquo;delete learn&rsquo;},{&lsquo;name&rsquo;:&rsquo;delete three&rsquo;,&rsquo;note&rsquo;:&rsquo;delete learn&rsquo;}])<br />
{<br />
    &ldquo;acknowledged&rdquo; : true,<br />
    &ldquo;insertedIds&rdquo; : [<br />
        ObjectId(&ldquo;5a406d6f46245769d3e9e045&rdquo;),<br />
        ObjectId(&ldquo;5a406d6f46245769d3e9e046&rdquo;),<br />
        ObjectId(&ldquo;5a406d6f46245769d3e9e047&rdquo;)<br />
    ]<br />
}<br />
</code></pre></p>
</li>
</ul>
<h3 id="36-update"><a name="user-content-36-update" href="#36-update" class="headeranchor-link" aria-hidden="true"><span class="headeranchor"></span></a>3.6 update</h3>
<ul>
<li>update更新一条记录</li>
</ul>
<pre><code>
rs0: PRIMARY> db.mycollection.insert({'name':'insert only one','note':'insert learn'})
WriteResult({ "nInserted" : 1 })
rs0: PRIMARY> db.mycollection.insert({'name':'insert only one','note':'insert learn'})
{
    "acknowledged" : true,
    "insertedId" : ObjectId("5a4058de46245769d3e9e034")
}
rs0: PRIMARY> db.mycollection.find()
{ "_id" : ObjectId("5a4058bf46245769d3e9e033"), "name" : "insert only one", "note" : "insert learn" }
{ "_id" : ObjectId("5a4058de46245769d3e9e034"), "name" : "insert only one", "note" : "insert learn" }
rs0: PRIMARY> db.mycollection.update({'name':'insert only one'},{$set:{'name':'update test'}})
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
rs0: PRIMARY> db.mycollection.find()
{ "_id" : ObjectId("5a4058bf46245769d3e9e033"), "name" : "update test", "note" : "insert learn" }
{ "_id" : ObjectId("5a4058de46245769d3e9e034"), "name" : "insert only one", "note" : "insert learn" }
</code></pre>

<ul>
<li>如果要修改多条相同的document，需要增加multi参数为true。</li>
</ul>
<pre><code>
 rs0: PRIMARY> db.mycollection.update({'note':'insert learn'},{$set:{'note':'update learn'}},{multi:true})
WriteResult({ "nMatched" : 2, "nUpserted" : 0, "nModified" : 2 })
 rs0: PRIMARY> db.mycollection.find()
{ "_id" : ObjectId("5a4058bf46245769d3e9e033"), "name" : "update test", "note" : "update learn" }
{ "_id" : ObjectId("5a4058de46245769d3e9e034"), "name" : "insert only one", "note" : "update learn" }
</code></pre>

<ul>
<li>其他更新语句</li>
</ul>
<pre><code>
db.mycollection.updateOne()
db.mycollection.updateMany()
db.mycollection.replaceOne()
</code></pre>

<h3 id="37-delete"><a name="user-content-37-delete" href="#37-delete" class="headeranchor-link" aria-hidden="true"><span class="headeranchor"></span></a>3.7 delete</h3>
<p>插入多条记录<br />
<pre><code><br />
rs0: PRIMARY&gt; db.mycollection.insert([{&lsquo;name&rsquo;:&rsquo;delete one&rsquo;,&rsquo;note&rsquo;:&rsquo;delete learn&rsquo;},{&lsquo;name&rsquo;:&rsquo;delete two&rsquo;,&rsquo;note&rsquo;:&rsquo;delete learn&rsquo;},{&lsquo;name&rsquo;:&rsquo;delete three&rsquo;,&rsquo;note&rsquo;:&rsquo;delete learn&rsquo;}])<br />
BulkWriteResult({<br />
    &ldquo;writeErrors&rdquo; : [ ],<br />
    &ldquo;writeConcernErrors&rdquo; : [ ],<br />
    &ldquo;nInserted&rdquo; : 3,<br />
    &ldquo;nUpserted&rdquo; : 0,<br />
    &ldquo;nMatched&rdquo; : 0,<br />
    &ldquo;nModified&rdquo; : 0,<br />
    &ldquo;nRemoved&rdquo; : 0,<br />
    &ldquo;upserted&rdquo; : [ ]<br />
})<br />
</code></pre></p>
<ul>
<li>删除一条记录</li>
</ul>
<pre><code>
rs0: PRIMARY> db.mycollection.deleteOne({'name':'delete one'})
{ "acknowledged" : true, "deletedCount" : 1 }
</code></pre>

<ul>
<li>删除多条记录</li>
</ul>
<pre><code>
rs0: PRIMARY> db.mycollection.deleteMany({'note':'delete learn'})
{ "acknowledged" : true, "deletedCount" : 2 }
</code></pre>

<ul>
<li>删除所有记录</li>
</ul>
<pre><code>
rs0: PRIMARY> db.mycollection.remove({})
</code></pre>

<h3 id="38-bulkwrite"><a name="user-content-38-bulkwrite" href="#38-bulkwrite" class="headeranchor-link" aria-hidden="true"><span class="headeranchor"></span></a>3.8 bulkWrite</h3>
<pre><code>
db.collection.bulkWrite(
   [
      { insertOne : <document> },
      { updateOne : <document> },
      { updateMany : <document> },
      { replaceOne : <document> },
      { deleteOne : <document> },
      { deleteMany : <document> }
   ],
   { ordered : false }
)
</code></pre>

<h3 id="39-query"><a name="user-content-39-query" href="#39-query" class="headeranchor-link" aria-hidden="true"><span class="headeranchor"></span></a>3.9 query</h3>
<ul>
<li>查询所有记录</li>
</ul>
<p><pre><code><br />
rs0: PRIMARY&gt; db.mycollection.find()<br />
SQL : select * from mytable;<br />
</code></pre></p>
<ul>
<li>条件查询</li>
</ul>
<pre><code>
rs0: PRIMARY> db.mycollection.find({'status':1})
SQL : select * from mytable where status = 1
</code></pre>

<ul>
<li>in查询</li>
</ul>
<pre><code>
rs0: PRIMARY> db.mycollection.find({'status':{$in[1,2]}})
SQL : select * from mytable where status in (1, 2)
</code></pre>

<ul>
<li>and查询</li>
</ul>
<pre><code>
rs0: PRIMARY> db.mycollection.find({'status':1,level:{$lt:3}})
SQL : select * from mytable where status = 1 and level < 3
</code></pre>

<ul>
<li>or查询</li>
</ul>
<pre><code>
rs0: PRIMARY> db.mycollection.find({$or:[{'status':1},{'level':{$lt:3}}]})
SQL : select * from mytable where status = 1 or level < 3
</code></pre>

<ul>
<li>and or 查询</li>
</ul>
<pre><code>
rs0: PRIMARY> db.mycollection.find({'status':1, $or:[{'level':{$lt:3}},{'time':{$gt:3}}]})
SQL : select * from mytable where status = 1 or (level < 3 and time > 3)
</code></pre>

<ul>
<li>嵌入式Embedded/Nested查询</li>
</ul>
<pre><code>
rs0:PRIMARY> db.mytest.insert( [
...    { item: "journal", qty: 25, size: { h: 14, w: 21, uom: "cm" }, status: "A" },
...    { item: "notebook", qty: 50, size: { h: 8.5, w: 11, uom: "in" }, status: "A" },
...    { item: "paper", qty: 100, size: { h: 8.5, w: 11, uom: "in" }, status: "D" },
...    { item: "planner", qty: 75, size: { h: 22.85, w: 30, uom: "cm" }, status: "D" },
...    { item: "postcard", qty: 45, size: { h: 10, w: 15.25, uom: "cm" }, status: "A" }
... ]);
BulkWriteResult({
    "writeErrors" : [ ],
    "writeConcernErrors" : [ ],
    "nInserted" : 5,
    "nUpserted" : 0,
    "nMatched" : 0,
    "nModified" : 0,
    "nRemoved" : 0,
    "upserted" : [ ]
})

rs0:PRIMARY> db.mytest.find({'size':{h:14,w:21,uom:'cm'}})
{ "_id" : ObjectId("5a40974246245769d3e9e049"), "item" : "journal", "qty" : 25, "size" : { "h" : 14, "w" : 21, "uom" : "cm" }, "status" : "A" }

rs0:PRIMARY> db.mytest.find({'size.h':{$gt:14}})
{ "_id" : ObjectId("5a40974246245769d3e9e04c"), "item" : "planner", "qty" : 75, "size" : { "h" : 22.85, "w" : 30, "uom" : "cm" }, "status" : "D" }

rs0:PRIMARY> db.mytest.find( { "size.h": { $lt: 15 }, "size.uom": "in", status: "D" } )
{ "_id" : ObjectId("5a40974246245769d3e9e04b"), "item" : "paper", "qty" : 100, "size" : { "h" : 8.5, "w" : 11, "uom" : "in" }, "status" : "D" }
</code></pre>

<ul>
<li>array查询</li>
</ul>
<p>插入test数据<br />
<pre><code><br />
rs0:PRIMARY&gt; db.mytest.insertMany([<br />
&hellip;    { item: &ldquo;journal&rdquo;, qty: 25, tags: [&ldquo;blank&rdquo;, &ldquo;red&rdquo;], dim_cm: [ 14, 21 ] },<br />
&hellip;    { item: &ldquo;notebook&rdquo;, qty: 50, tags: [&ldquo;red&rdquo;, &ldquo;blank&rdquo;], dim_cm: [ 14, 21 ] },<br />
&hellip;    { item: &ldquo;paper&rdquo;, qty: 100, tags: [&ldquo;red&rdquo;, &ldquo;blank&rdquo;, &ldquo;plain&rdquo;], dim_cm: [ 14, 21 ] },<br />
&hellip;    { item: &ldquo;planner&rdquo;, qty: 75, tags: [&ldquo;blank&rdquo;, &ldquo;red&rdquo;], dim_cm: [ 22.85, 30 ] },<br />
&hellip;    { item: &ldquo;postcard&rdquo;, qty: 45, tags: [&ldquo;blue&rdquo;], dim_cm: [ 10, 15.25 ] }<br />
&hellip; ]);<br />
{<br />
    &ldquo;acknowledged&rdquo; : true,<br />
    &ldquo;insertedIds&rdquo; : [<br />
        ObjectId(&ldquo;5a409a4046245769d3e9e04e&rdquo;),<br />
        ObjectId(&ldquo;5a409a4046245769d3e9e04f&rdquo;),<br />
        ObjectId(&ldquo;5a409a4046245769d3e9e050&rdquo;),<br />
        ObjectId(&ldquo;5a409a4046245769d3e9e051&rdquo;),<br />
        ObjectId(&ldquo;5a409a4046245769d3e9e052&rdquo;)<br />
    ]<br />
}<br />
</code></pre></p>
<p>精确查询整个数组</p>
<pre><code>
rs0:PRIMARY> db.mytest.find({'tags':['blank','red']})
{ "_id" : ObjectId("5a409a4046245769d3e9e04e"), "item" : "journal", "qty" : 25, "tags" : [ "blank", "red" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e051"), "item" : "planner", "qty" : 75, "tags" : [ "blank", "red" ], "dim_cm" : [ 22.85, 30 ] }
</code></pre>

<p>不按顺序查询数组</p>
<pre><code>
rs0:PRIMARY> db.mytest.find({'tags':{$all:['blank','red']}})
{ "_id" : ObjectId("5a409a4046245769d3e9e04e"), "item" : "journal", "qty" : 25, "tags" : [ "blank", "red" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e04f"), "item" : "notebook", "qty" : 50, "tags" : [ "red", "blank" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e050"), "item" : "paper", "qty" : 100, "tags" : [ "red", "blank", "plain" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e051"), "item" : "planner", "qty" : 75, "tags" : [ "blank", "red" ], "dim_cm" : [ 22.85, 30 ] }
</code></pre>

<p>查询数组的一个元素</p>
<pre><code>
rs0:PRIMARY> db.mytest.find({'tags':'red'})
{ "_id" : ObjectId("5a409a4046245769d3e9e04e"), "item" : "journal", "qty" : 25, "tags" : [ "blank", "red" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e04f"), "item" : "notebook", "qty" : 50, "tags" : [ "red", "blank" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e050"), "item" : "paper", "qty" : 100, "tags" : [ "red", "blank", "plain" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e051"), "item" : "planner", "qty" : 75, "tags" : [ "blank", "red" ], "dim_cm" : [ 22.85, 30 ] }
</code></pre>

<p>数组的条件查询</p>
<pre><code>
rs0:PRIMARY> db.mytest.find({'dim_cm':{$gt:25}})
{ "_id" : ObjectId("5a409a4046245769d3e9e051"), "item" : "planner", "qty" : 75, "tags" : [ "blank", "red" ], "dim_cm" : [ 22.85, 30 ] }

rs0:PRIMARY> db.mytest.find({'dim_cm':{$gt:22,$lt:25}})
{ "_id" : ObjectId("5a409a4046245769d3e9e051"), "item" : "planner", "qty" : 75, "tags" : [ "blank", "red" ], "dim_cm" : [ 22.85, 30 ] }
</code></pre>

<p>指定元素查询<br />
<pre><code><br />
rs0:PRIMARY&gt; db.mytest.find({&lsquo;dim_cm.0&rsquo;:{$gt:22}})<br />
{ &ldquo;_id&rdquo; : ObjectId(&ldquo;5a409a4046245769d3e9e051&rdquo;), &ldquo;item&rdquo; : &ldquo;planner&rdquo;, &ldquo;qty&rdquo; : 75, &ldquo;tags&rdquo; : [ &ldquo;blank&rdquo;, &ldquo;red&rdquo; ], &ldquo;dim_cm&rdquo; : [ 22.85, 30 ] }<br />
</code></pre></p>
<p>数组元素个数查询</p>
<pre><code>
rs0:PRIMARY> db.mytest.find({'dim_cm':{$size:2}})
{ "_id" : ObjectId("5a409a4046245769d3e9e04e"), "item" : "journal", "qty" : 25, "tags" : [ "blank", "red" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e04f"), "item" : "notebook", "qty" : 50, "tags" : [ "red", "blank" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e050"), "item" : "paper", "qty" : 100, "tags" : [ "red", "blank", "plain" ], "dim_cm" : [ 14, 21 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e051"), "item" : "planner", "qty" : 75, "tags" : [ "blank", "red" ], "dim_cm" : [ 22.85, 30 ] }
{ "_id" : ObjectId("5a409a4046245769d3e9e052"), "item" : "postcard", "qty" : 45, "tags" : [ "blue" ], "dim_cm" : [ 10, 15.25 ] }
rs0:PRIMARY>
rs0:PRIMARY> db.mytest.find({'dim_cm':{$size:3}})
rs0:PRIMARY>
</code></pre>

<ul>
<li>数组内嵌</li>
</ul>
<p>插入测试数据<br />
<pre><code><br />
rs0:PRIMARY&gt; db.mytest.insertMany( [<br />
&hellip;    { item: &ldquo;journal&rdquo;, instock: [ { warehouse: &ldquo;A&rdquo;, qty: 5 }, { warehouse: &ldquo;C&rdquo;, qty: 15 } ] },<br />
&hellip;    { item: &ldquo;notebook&rdquo;, instock: [ { warehouse: &ldquo;C&rdquo;, qty: 5 } ] },<br />
&hellip;    { item: &ldquo;paper&rdquo;, instock: [ { warehouse: &ldquo;A&rdquo;, qty: 60 }, { warehouse: &ldquo;B&rdquo;, qty: 15 } ] },<br />
&hellip;    { item: &ldquo;planner&rdquo;, instock: [ { warehouse: &ldquo;A&rdquo;, qty: 40 }, { warehouse: &ldquo;B&rdquo;, qty: 5 } ] },<br />
&hellip;    { item: &ldquo;postcard&rdquo;, instock: [ { warehouse: &ldquo;B&rdquo;, qty: 15 }, { warehouse: &ldquo;C&rdquo;, qty: 35 } ] }<br />
&hellip; ]);<br />
{<br />
    &ldquo;acknowledged&rdquo; : true,<br />
    &ldquo;insertedIds&rdquo; : [<br />
        ObjectId(&ldquo;5a409f6446245769d3e9e053&rdquo;),<br />
        ObjectId(&ldquo;5a409f6446245769d3e9e054&rdquo;),<br />
        ObjectId(&ldquo;5a409f6446245769d3e9e055&rdquo;),<br />
        ObjectId(&ldquo;5a409f6446245769d3e9e056&rdquo;),<br />
        ObjectId(&ldquo;5a409f6446245769d3e9e057&rdquo;)<br />
    ]<br />
}<br />
</code></pre></p>
<p>数组内嵌查询，必须按照顺序才能匹配，不按照顺序无法匹配到<br />
<pre><code><br />
rs0:PRIMARY&gt; db.mytest.find( { &ldquo;instock&rdquo;: { warehouse: &ldquo;A&rdquo;, qty: 5 } } )<br />
{ &ldquo;_id&rdquo; : ObjectId(&ldquo;5a409f6446245769d3e9e053&rdquo;), &ldquo;item&rdquo; : &ldquo;journal&rdquo;, &ldquo;instock&rdquo; : [ { &ldquo;warehouse&rdquo; : &ldquo;A&rdquo;, &ldquo;qty&rdquo; : 5 }, { &ldquo;warehouse&rdquo; : &ldquo;C&rdquo;, &ldquo;qty&rdquo; : 15 } ] }<br />
rs0:PRIMARY&gt; db.mytest.find( { &ldquo;instock&rdquo;: { qty: 5,warehouse: &ldquo;A&rdquo; } } )<br />
rs0:PRIMARY&gt;<br />
rs0:PRIMARY&gt;<br />
</code></pre></p>
<p>数组字段的条件查询，&rsquo;.&rsquo;的使用</p>
<pre><code>
rs0:PRIMARY> db.mytest.find( { "instock.qty": {$gt:40 } } )
{ "_id" : ObjectId("5a409f6446245769d3e9e055"), "item" : "paper", "instock" : [ { "warehouse" : "A", "qty" : 60 }, { "warehouse" : "B", "qty" : 15 } ] }
</code></pre>

<p>数组内嵌按元素查询</p>
<pre><code>
rs0:PRIMARY> db.mytest.find( { "instock.0.qty": {$gt:40 } } )
{ "_id" : ObjectId("5a409f6446245769d3e9e055"), "item" : "paper", "instock" : [ { "warehouse" : "A", "qty" : 60 }, { "warehouse" : "B", "qty" : 15 } ] }
rs0:PRIMARY> db.mytest.find( { "instock.1.qty": {$gt:20 } } )
{ "_id" : ObjectId("5a409f6446245769d3e9e057"), "item" : "postcard", "instock" : [ { "warehouse" : "B", "qty" : 15 }, { "warehouse" : "C", "qty" : 35 } ] }
</code></pre>

<p>多条件查询</p>
<pre><code>
rs0:PRIMARY> db.mytest.find( { "instock.qty": 5, "instock.warehouse": "A" } )
{ "_id" : ObjectId("5a409f6446245769d3e9e053"), "item" : "journal", "instock" : [ { "warehouse" : "A", "qty" : 5 }, { "warehouse" : "C", "qty" : 15 } ] }
{ "_id" : ObjectId("5a409f6446245769d3e9e056"), "item" : "planner", "instock" : [ { "warehouse" : "A", "qty" : 40 }, { "warehouse" : "B", "qty" : 5 } ] }
</code></pre></article></body></html>