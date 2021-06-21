---
title: Chris Humphrey
layout: default
---

<div class="mid-section-cover" >
    <nav>

        <h1><a href="/" style="color:#000000;text-decoration:none;">{{ site.author_name }}</a></h1>
        

    </nav>
    <main class="sub-mid-section-cover">      
        {{ content }}

        
<h2 style="text-align: center;">&nbsp;&nbsp;</h2>
<h2 style="text-align: center;">Visualizing and Mapping Restaurants in Portland</h2>
<p style="text-align: justify;">Portland is a great city that I was fortunate to spend some time in this Summer. It's a city with an interesting vibe, and equally interesting restaurants. I came across a dataset provided by Yelp, and thought combing through the data would make for a fun project in data visualization. The dataset is a JSON file which contains (assumingly) all restaurants in Portland, along with attributes such as which cuisine they serve, and their GPS coordinates.</p>
<p style="text-align: justify;">&nbsp; &nbsp;&nbsp;</p>
<p style="text-align: justify;">I will be making two visualizations. After cleaning the data, I will make a violin plot showing the distribution of Yelp reviews in Portland, aggregated by cuisine type (Italien, American, Japanese, ...). Second, I will make a heatmap of the locations of restaurants scaled by the average rating of said restaurants.</p>
<p style="text-align: justify;">&nbsp;&nbsp;</p>
<p style="text-align: justify;">&nbsp;&nbsp;</p>
<p style="text-align: justify;">&nbsp;&nbsp;</p>
<p style="text-align: justify;">&nbsp;&nbsp;</p>
<p style="text-align: justify;">&nbsp;&nbsp;</p>
        
        
<html>
<head><meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Untitled-Copy1</title><script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>

    
    
    
    
    



<style type="text/css">
    pre { line-height: 125%; }
td.linenos .normal { color: inherit; background-color: transparent; padding-left: 5px; padding-right: 5px; }
span.linenos { color: inherit; background-color: transparent; padding-left: 5px; padding-right: 5px; }
td.linenos .special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
span.linenos.special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
.highlight .hll { background-color: var(--jp-cell-editor-active-background) }
.highlight { background: var(--jp-cell-editor-background); color: var(--jp-mirror-editor-variable-color) }
.highlight .c { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment */
.highlight .err { color: var(--jp-mirror-editor-error-color) } /* Error */
.highlight .k { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword */
.highlight .o { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator */
.highlight .p { color: var(--jp-mirror-editor-punctuation-color) } /* Punctuation */
.highlight .ch { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Multiline */
.highlight .cp { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Preproc */
.highlight .cpf { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Single */
.highlight .cs { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Special */
.highlight .kc { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Pseudo */
.highlight .kr { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Type */
.highlight .m { color: var(--jp-mirror-editor-number-color) } /* Literal.Number */
.highlight .s { color: var(--jp-mirror-editor-string-color) } /* Literal.String */
.highlight .ow { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator.Word */
.highlight .w { color: var(--jp-mirror-editor-variable-color) } /* Text.Whitespace */
.highlight .mb { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Bin */
.highlight .mf { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Float */
.highlight .mh { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Hex */
.highlight .mi { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer */
.highlight .mo { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Oct */
.highlight .sa { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Affix */
.highlight .sb { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Backtick */
.highlight .sc { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Char */
.highlight .dl { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Delimiter */
.highlight .sd { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Doc */
.highlight .s2 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Double */
.highlight .se { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Escape */
.highlight .sh { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Heredoc */
.highlight .si { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Interpol */
.highlight .sx { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Other */
.highlight .sr { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Regex */
.highlight .s1 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Single */
.highlight .ss { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Symbol */
.highlight .il { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer.Long */
  </style>



<style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
 * Mozilla scrollbar styling
 */

/* use standard opaque scrollbars for most nodes */
[data-jp-theme-scrollbars='true'] {
  scrollbar-color: rgb(var(--jp-scrollbar-thumb-color))
    var(--jp-scrollbar-background-color);
}

/* for code nodes, use a transparent style of scrollbar. These selectors
 * will match lower in the tree, and so will override the above */
[data-jp-theme-scrollbars='true'] .CodeMirror-hscrollbar,
[data-jp-theme-scrollbars='true'] .CodeMirror-vscrollbar {
  scrollbar-color: rgba(var(--jp-scrollbar-thumb-color), 0.5) transparent;
}

/*
 * Webkit scrollbar styling
 */

/* use standard opaque scrollbars for most nodes */

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar,
[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-corner {
  background: var(--jp-scrollbar-background-color);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-thumb {
  background: rgb(var(--jp-scrollbar-thumb-color));
  border: var(--jp-scrollbar-thumb-margin) solid transparent;
  background-clip: content-box;
  border-radius: var(--jp-scrollbar-thumb-radius);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-track:horizontal {
  border-left: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
  border-right: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-track:vertical {
  border-top: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
  border-bottom: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
}

/* for code nodes, use a transparent style of scrollbar */

[data-jp-theme-scrollbars='true'] .CodeMirror-hscrollbar::-webkit-scrollbar,
[data-jp-theme-scrollbars='true'] .CodeMirror-vscrollbar::-webkit-scrollbar,
[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-corner,
[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-corner {
  background-color: transparent;
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-thumb,
[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-thumb {
  background: rgba(var(--jp-scrollbar-thumb-color), 0.5);
  border: var(--jp-scrollbar-thumb-margin) solid transparent;
  background-clip: content-box;
  border-radius: var(--jp-scrollbar-thumb-radius);
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-track:horizontal {
  border-left: var(--jp-scrollbar-endpad) solid transparent;
  border-right: var(--jp-scrollbar-endpad) solid transparent;
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-track:vertical {
  border-top: var(--jp-scrollbar-endpad) solid transparent;
  border-bottom: var(--jp-scrollbar-endpad) solid transparent;
}

/*
 * Phosphor
 */

.lm-ScrollBar[data-orientation='horizontal'] {
  min-height: 16px;
  max-height: 16px;
  min-width: 45px;
  border-top: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] {
  min-width: 16px;
  max-width: 16px;
  min-height: 45px;
  border-left: 1px solid #a0a0a0;
}

.lm-ScrollBar-button {
  background-color: #f0f0f0;
  background-position: center center;
  min-height: 15px;
  max-height: 15px;
  min-width: 15px;
  max-width: 15px;
}

.lm-ScrollBar-button:hover {
  background-color: #dadada;
}

.lm-ScrollBar-button.lm-mod-active {
  background-color: #cdcdcd;
}

.lm-ScrollBar-track {
  background: #f0f0f0;
}

.lm-ScrollBar-thumb {
  background: #cdcdcd;
}

.lm-ScrollBar-thumb:hover {
  background: #bababa;
}

.lm-ScrollBar-thumb.lm-mod-active {
  background: #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal'] .lm-ScrollBar-thumb {
  height: 100%;
  min-width: 15px;
  border-left: 1px solid #a0a0a0;
  border-right: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] .lm-ScrollBar-thumb {
  width: 100%;
  min-height: 15px;
  border-top: 1px solid #a0a0a0;
  border-bottom: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-left);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-right);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-up);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-down);
  background-size: 17px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-Widget, /* </DEPRECATED> */
.lm-Widget {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  cursor: default;
}


/* <DEPRECATED> */ .p-Widget.p-mod-hidden, /* </DEPRECATED> */
.lm-Widget.lm-mod-hidden {
  display: none !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-CommandPalette, /* </DEPRECATED> */
.lm-CommandPalette {
  display: flex;
  flex-direction: column;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-CommandPalette-search, /* </DEPRECATED> */
.lm-CommandPalette-search {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-content, /* </DEPRECATED> */
.lm-CommandPalette-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  min-height: 0;
  overflow: auto;
  list-style-type: none;
}


/* <DEPRECATED> */ .p-CommandPalette-header, /* </DEPRECATED> */
.lm-CommandPalette-header {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}


/* <DEPRECATED> */ .p-CommandPalette-item, /* </DEPRECATED> */
.lm-CommandPalette-item {
  display: flex;
  flex-direction: row;
}


/* <DEPRECATED> */ .p-CommandPalette-itemIcon, /* </DEPRECATED> */
.lm-CommandPalette-itemIcon {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-itemContent, /* </DEPRECATED> */
.lm-CommandPalette-itemContent {
  flex: 1 1 auto;
  overflow: hidden;
}


/* <DEPRECATED> */ .p-CommandPalette-itemShortcut, /* </DEPRECATED> */
.lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-itemLabel, /* </DEPRECATED> */
.lm-CommandPalette-itemLabel {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-DockPanel, /* </DEPRECATED> */
.lm-DockPanel {
  z-index: 0;
}


/* <DEPRECATED> */ .p-DockPanel-widget, /* </DEPRECATED> */
.lm-DockPanel-widget {
  z-index: 0;
}


/* <DEPRECATED> */ .p-DockPanel-tabBar, /* </DEPRECATED> */
.lm-DockPanel-tabBar {
  z-index: 1;
}


/* <DEPRECATED> */ .p-DockPanel-handle, /* </DEPRECATED> */
.lm-DockPanel-handle {
  z-index: 2;
}


/* <DEPRECATED> */ .p-DockPanel-handle.p-mod-hidden, /* </DEPRECATED> */
.lm-DockPanel-handle.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-DockPanel-handle:after, /* </DEPRECATED> */
.lm-DockPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='horizontal'],
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='horizontal'] {
  cursor: ew-resize;
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='vertical'],
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='vertical'] {
  cursor: ns-resize;
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='horizontal']:after,
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='horizontal']:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='vertical']:after,
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='vertical']:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}


/* <DEPRECATED> */ .p-DockPanel-overlay, /* </DEPRECATED> */
.lm-DockPanel-overlay {
  z-index: 3;
  box-sizing: border-box;
  pointer-events: none;
}


/* <DEPRECATED> */ .p-DockPanel-overlay.p-mod-hidden, /* </DEPRECATED> */
.lm-DockPanel-overlay.lm-mod-hidden {
  display: none !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-Menu, /* </DEPRECATED> */
.lm-Menu {
  z-index: 10000;
  position: absolute;
  white-space: nowrap;
  overflow-x: hidden;
  overflow-y: auto;
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-Menu-content, /* </DEPRECATED> */
.lm-Menu-content {
  margin: 0;
  padding: 0;
  display: table;
  list-style-type: none;
}


/* <DEPRECATED> */ .p-Menu-item, /* </DEPRECATED> */
.lm-Menu-item {
  display: table-row;
}


/* <DEPRECATED> */
.p-Menu-item.p-mod-hidden,
.p-Menu-item.p-mod-collapsed,
/* </DEPRECATED> */
.lm-Menu-item.lm-mod-hidden,
.lm-Menu-item.lm-mod-collapsed {
  display: none !important;
}


/* <DEPRECATED> */
.p-Menu-itemIcon,
.p-Menu-itemSubmenuIcon,
/* </DEPRECATED> */
.lm-Menu-itemIcon,
.lm-Menu-itemSubmenuIcon {
  display: table-cell;
  text-align: center;
}


/* <DEPRECATED> */ .p-Menu-itemLabel, /* </DEPRECATED> */
.lm-Menu-itemLabel {
  display: table-cell;
  text-align: left;
}


/* <DEPRECATED> */ .p-Menu-itemShortcut, /* </DEPRECATED> */
.lm-Menu-itemShortcut {
  display: table-cell;
  text-align: right;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-MenuBar, /* </DEPRECATED> */
.lm-MenuBar {
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-MenuBar-content, /* </DEPRECATED> */
.lm-MenuBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: row;
  list-style-type: none;
}


/* <DEPRECATED> */ .p--MenuBar-item, /* </DEPRECATED> */
.lm-MenuBar-item {
  box-sizing: border-box;
}


/* <DEPRECATED> */
.p-MenuBar-itemIcon,
.p-MenuBar-itemLabel,
/* </DEPRECATED> */
.lm-MenuBar-itemIcon,
.lm-MenuBar-itemLabel {
  display: inline-block;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-ScrollBar, /* </DEPRECATED> */
.lm-ScrollBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */
.p-ScrollBar[data-orientation='horizontal'],
/* </DEPRECATED> */
.lm-ScrollBar[data-orientation='horizontal'] {
  flex-direction: row;
}


/* <DEPRECATED> */
.p-ScrollBar[data-orientation='vertical'],
/* </DEPRECATED> */
.lm-ScrollBar[data-orientation='vertical'] {
  flex-direction: column;
}


/* <DEPRECATED> */ .p-ScrollBar-button, /* </DEPRECATED> */
.lm-ScrollBar-button {
  box-sizing: border-box;
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-ScrollBar-track, /* </DEPRECATED> */
.lm-ScrollBar-track {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  flex: 1 1 auto;
}


/* <DEPRECATED> */ .p-ScrollBar-thumb, /* </DEPRECATED> */
.lm-ScrollBar-thumb {
  box-sizing: border-box;
  position: absolute;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-SplitPanel-child, /* </DEPRECATED> */
.lm-SplitPanel-child {
  z-index: 0;
}


/* <DEPRECATED> */ .p-SplitPanel-handle, /* </DEPRECATED> */
.lm-SplitPanel-handle {
  z-index: 1;
}


/* <DEPRECATED> */ .p-SplitPanel-handle.p-mod-hidden, /* </DEPRECATED> */
.lm-SplitPanel-handle.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-SplitPanel-handle:after, /* </DEPRECATED> */
.lm-SplitPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='horizontal'] > .p-SplitPanel-handle,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle {
  cursor: ew-resize;
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='vertical'] > .p-SplitPanel-handle,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle {
  cursor: ns-resize;
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='horizontal'] > .p-SplitPanel-handle:after,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='vertical'] > .p-SplitPanel-handle:after,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-TabBar, /* </DEPRECATED> */
.lm-TabBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-TabBar[data-orientation='horizontal'], /* </DEPRECATED> */
.lm-TabBar[data-orientation='horizontal'] {
  flex-direction: row;
}


/* <DEPRECATED> */ .p-TabBar[data-orientation='vertical'], /* </DEPRECATED> */
.lm-TabBar[data-orientation='vertical'] {
  flex-direction: column;
}


/* <DEPRECATED> */ .p-TabBar-content, /* </DEPRECATED> */
.lm-TabBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex: 1 1 auto;
  list-style-type: none;
}


/* <DEPRECATED> */
.p-TabBar[data-orientation='horizontal'] > .p-TabBar-content,
/* </DEPRECATED> */
.lm-TabBar[data-orientation='horizontal'] > .lm-TabBar-content {
  flex-direction: row;
}


/* <DEPRECATED> */
.p-TabBar[data-orientation='vertical'] > .p-TabBar-content,
/* </DEPRECATED> */
.lm-TabBar[data-orientation='vertical'] > .lm-TabBar-content {
  flex-direction: column;
}


/* <DEPRECATED> */ .p-TabBar-tab, /* </DEPRECATED> */
.lm-TabBar-tab {
  display: flex;
  flex-direction: row;
  box-sizing: border-box;
  overflow: hidden;
}


/* <DEPRECATED> */
.p-TabBar-tabIcon,
.p-TabBar-tabCloseIcon,
/* </DEPRECATED> */
.lm-TabBar-tabIcon,
.lm-TabBar-tabCloseIcon {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-TabBar-tabLabel, /* </DEPRECATED> */
.lm-TabBar-tabLabel {
  flex: 1 1 auto;
  overflow: hidden;
  white-space: nowrap;
}


/* <DEPRECATED> */ .p-TabBar-tab.p-mod-hidden, /* </DEPRECATED> */
.lm-TabBar-tab.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-TabBar.p-mod-dragging .p-TabBar-tab, /* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging .lm-TabBar-tab {
  position: relative;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging[data-orientation='horizontal'] .p-TabBar-tab,
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging[data-orientation='horizontal'] .lm-TabBar-tab {
  left: 0;
  transition: left 150ms ease;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging[data-orientation='vertical'] .p-TabBar-tab,
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging[data-orientation='vertical'] .lm-TabBar-tab {
  top: 0;
  transition: top 150ms ease;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging .p-TabBar-tab.p-mod-dragging
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging .lm-TabBar-tab.lm-mod-dragging {
  transition: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-TabPanel-tabBar, /* </DEPRECATED> */
.lm-TabPanel-tabBar {
  z-index: 1;
}


/* <DEPRECATED> */ .p-TabPanel-stackedPanel, /* </DEPRECATED> */
.lm-TabPanel-stackedPanel {
  z-index: 0;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

@charset "UTF-8";
/*!

Copyright 2015-present Palantir Technologies, Inc. All rights reserved.
Licensed under the Apache License, Version 2.0.

*/
html{
  -webkit-box-sizing:border-box;
          box-sizing:border-box; }

*,
*::before,
*::after{
  -webkit-box-sizing:inherit;
          box-sizing:inherit; }

body{
  text-transform:none;
  line-height:1.28581;
  letter-spacing:0;
  font-size:14px;
  font-weight:400;
  color:#182026;
  font-family:-apple-system, "BlinkMacSystemFont", "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Open Sans", "Helvetica Neue", "Icons16", sans-serif; }

p{
  margin-top:0;
  margin-bottom:10px; }

small{
  font-size:12px; }

  
strong{
  font-weight:600; }

::-moz-selection{
  background:rgba(125, 188, 255, 0.6); }

::selection{
  background:rgba(125, 188, 255, 0.6); }
.bp3-heading{
  color:#182026;
  font-weight:600;
  margin:0 0 10px;
  padding:0; }
  .bp3-dark .bp3-heading{
    color:#f5f8fa; }

h1.bp3-heading, .bp3-running-text h1{
  line-height:40px;
  font-size:36px; }

h2.bp3-heading, .bp3-running-text h2{
  line-height:32px;
  font-size:28px; }

h3.bp3-heading, .bp3-running-text h3{
  line-height:25px;
  font-size:22px; }

h4.bp3-heading, .bp3-running-text h4{
  line-height:21px;
  font-size:18px; }

h5.bp3-heading, .bp3-running-text h5{
  line-height:19px;
  font-size:16px; }

h6.bp3-heading, .bp3-running-text h6{
  line-height:16px;
  font-size:14px; }
.bp3-ui-text{
  text-transform:none;
  line-height:1.28581;
  letter-spacing:0;
  font-size:14px;
  font-weight:400; }

.bp3-monospace-text{
  text-transform:none;
  font-family:monospace; }

.bp3-text-muted{
  color:#5c7080; }
  .bp3-dark .bp3-text-muted{
    color:#a7b6c2; }

.bp3-text-disabled{
  color:rgba(92, 112, 128, 0.6); }
  .bp3-dark .bp3-text-disabled{
    color:rgba(167, 182, 194, 0.6); }

.bp3-text-overflow-ellipsis{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal; }
.bp3-running-text{
  line-height:1.5;
  font-size:14px; }
  .bp3-running-text h1{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h1{
      color:#f5f8fa; }
  .bp3-running-text h2{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h2{
      color:#f5f8fa; }
  .bp3-running-text h3{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h3{
      color:#f5f8fa; }
  .bp3-running-text h4{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h4{
      color:#f5f8fa; }
  .bp3-running-text h5{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h5{
      color:#f5f8fa; }
  .bp3-running-text h6{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h6{
      color:#f5f8fa; }
  .bp3-running-text hr{
    margin:20px 0;
    border:none;
    border-bottom:1px solid rgba(16, 22, 26, 0.15); }
    .bp3-dark .bp3-running-text hr{
      border-color:rgba(255, 255, 255, 0.15); }
  .bp3-running-text p{
    margin:0 0 10px;
    padding:0; }

.bp3-text-large{
  font-size:16px; }

.bp3-text-small{
  font-size:12px; }
a{
  text-decoration:none;
  color:#106ba3; }
  a:hover{
    cursor:pointer;
    text-decoration:underline;
    color:#106ba3; }
  a .bp3-icon, a .bp3-icon-standard, a .bp3-icon-large{
    color:inherit; }
  a code,
  .bp3-dark a code{
    color:inherit; }
  .bp3-dark a,
  .bp3-dark a:hover{
    color:#48aff0; }
    .bp3-dark a .bp3-icon, .bp3-dark a .bp3-icon-standard, .bp3-dark a .bp3-icon-large,
    .bp3-dark a:hover .bp3-icon,
    .bp3-dark a:hover .bp3-icon-standard,
    .bp3-dark a:hover .bp3-icon-large{
      color:inherit; }
.bp3-running-text code, .bp3-code{
  text-transform:none;
  font-family:monospace;
  border-radius:3px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2);
  background:rgba(255, 255, 255, 0.7);
  padding:2px 5px;
  color:#5c7080;
  font-size:smaller; }
  .bp3-dark .bp3-running-text code, .bp3-running-text .bp3-dark code, .bp3-dark .bp3-code{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#a7b6c2; }
  .bp3-running-text a > code, a > .bp3-code{
    color:#137cbd; }
    .bp3-dark .bp3-running-text a > code, .bp3-running-text .bp3-dark a > code, .bp3-dark a > .bp3-code{
      color:inherit; }

.bp3-running-text pre, .bp3-code-block{
  text-transform:none;
  font-family:monospace;
  display:block;
  margin:10px 0;
  border-radius:3px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
  background:rgba(255, 255, 255, 0.7);
  padding:13px 15px 12px;
  line-height:1.4;
  color:#182026;
  font-size:13px;
  word-break:break-all;
  word-wrap:break-word; }
  .bp3-dark .bp3-running-text pre, .bp3-running-text .bp3-dark pre, .bp3-dark .bp3-code-block{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa; }
  .bp3-running-text pre > code, .bp3-code-block > code{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none;
    padding:0;
    color:inherit;
    font-size:inherit; }

.bp3-running-text kbd, .bp3-key{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  min-width:24px;
  height:24px;
  padding:3px 6px;
  vertical-align:middle;
  line-height:24px;
  color:#5c7080;
  font-family:inherit;
  font-size:12px; }
  .bp3-running-text kbd .bp3-icon, .bp3-key .bp3-icon, .bp3-running-text kbd .bp3-icon-standard, .bp3-key .bp3-icon-standard, .bp3-running-text kbd .bp3-icon-large, .bp3-key .bp3-icon-large{
    margin-right:5px; }
  .bp3-dark .bp3-running-text kbd, .bp3-running-text .bp3-dark kbd, .bp3-dark .bp3-key{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
    background:#394b59;
    color:#a7b6c2; }
.bp3-running-text blockquote, .bp3-blockquote{
  margin:0 0 10px;
  border-left:solid 4px rgba(167, 182, 194, 0.5);
  padding:0 20px; }
  .bp3-dark .bp3-running-text blockquote, .bp3-running-text .bp3-dark blockquote, .bp3-dark .bp3-blockquote{
    border-color:rgba(115, 134, 148, 0.5); }
.bp3-running-text ul,
.bp3-running-text ol, .bp3-list{
  margin:10px 0;
  padding-left:30px; }
  .bp3-running-text ul li:not(:last-child), .bp3-running-text ol li:not(:last-child), .bp3-list li:not(:last-child){
    margin-bottom:5px; }
  .bp3-running-text ul ol, .bp3-running-text ol ol, .bp3-list ol,
  .bp3-running-text ul ul,
  .bp3-running-text ol ul,
  .bp3-list ul{
    margin-top:5px; }

.bp3-list-unstyled{
  margin:0;
  padding:0;
  list-style:none; }
  .bp3-list-unstyled li{
    padding:0; }
.bp3-rtl{
  text-align:right; }

.bp3-dark{
  color:#f5f8fa; }

:focus{
  outline:rgba(19, 124, 189, 0.6) auto 2px;
  outline-offset:2px;
  -moz-outline-radius:6px; }

.bp3-focus-disabled :focus{
  outline:none !important; }
  .bp3-focus-disabled :focus ~ .bp3-control-indicator{
    outline:none !important; }

.bp3-alert{
  max-width:400px;
  padding:20px; }

.bp3-alert-body{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex; }
  .bp3-alert-body .bp3-icon{
    margin-top:0;
    margin-right:20px;
    font-size:40px; }

.bp3-alert-footer{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:reverse;
      -ms-flex-direction:row-reverse;
          flex-direction:row-reverse;
  margin-top:10px; }
  .bp3-alert-footer .bp3-button{
    margin-left:10px; }
.bp3-breadcrumbs{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-wrap:wrap;
      flex-wrap:wrap;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  margin:0;
  cursor:default;
  height:30px;
  padding:0;
  list-style:none; }
  .bp3-breadcrumbs > li{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center; }
    .bp3-breadcrumbs > li::after{
      display:block;
      margin:0 5px;
      background:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M10.71 7.29l-4-4a1.003 1.003 0 0 0-1.42 1.42L8.59 8 5.3 11.29c-.19.18-.3.43-.3.71a1.003 1.003 0 0 0 1.71.71l4-4c.18-.18.29-.43.29-.71 0-.28-.11-.53-.29-.71z' fill='%235C7080'/%3e%3c/svg%3e");
      width:16px;
      height:16px;
      content:""; }
    .bp3-breadcrumbs > li:last-of-type::after{
      display:none; }

.bp3-breadcrumb,
.bp3-breadcrumb-current,
.bp3-breadcrumbs-collapsed{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  font-size:16px; }

.bp3-breadcrumb,
.bp3-breadcrumbs-collapsed{
  color:#5c7080; }

.bp3-breadcrumb:hover{
  text-decoration:none; }

.bp3-breadcrumb.bp3-disabled{
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-breadcrumb .bp3-icon{
  margin-right:5px; }

.bp3-breadcrumb-current{
  color:inherit;
  font-weight:600; }
  .bp3-breadcrumb-current .bp3-input{
    vertical-align:baseline;
    font-size:inherit;
    font-weight:inherit; }

.bp3-breadcrumbs-collapsed{
  margin-right:2px;
  border:none;
  border-radius:3px;
  background:#ced9e0;
  cursor:pointer;
  padding:1px 5px;
  vertical-align:text-bottom; }
  .bp3-breadcrumbs-collapsed::before{
    display:block;
    background:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cg fill='%235C7080'%3e%3ccircle cx='2' cy='8.03' r='2'/%3e%3ccircle cx='14' cy='8.03' r='2'/%3e%3ccircle cx='8' cy='8.03' r='2'/%3e%3c/g%3e%3c/svg%3e") center no-repeat;
    width:16px;
    height:16px;
    content:""; }
  .bp3-breadcrumbs-collapsed:hover{
    background:#bfccd6;
    text-decoration:none;
    color:#182026; }

.bp3-dark .bp3-breadcrumb,
.bp3-dark .bp3-breadcrumbs-collapsed{
  color:#a7b6c2; }

.bp3-dark .bp3-breadcrumbs > li::after{
  color:#a7b6c2; }

.bp3-dark .bp3-breadcrumb.bp3-disabled{
  color:rgba(167, 182, 194, 0.6); }

.bp3-dark .bp3-breadcrumb-current{
  color:#f5f8fa; }

.bp3-dark .bp3-breadcrumbs-collapsed{
  background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-breadcrumbs-collapsed:hover{
    background:rgba(16, 22, 26, 0.6);
    color:#f5f8fa; }
.bp3-button{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  border:none;
  border-radius:3px;
  cursor:pointer;
  padding:5px 10px;
  vertical-align:middle;
  text-align:left;
  font-size:14px;
  min-width:30px;
  min-height:30px; }
  .bp3-button > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-button > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-button::before,
  .bp3-button > *{
    margin-right:7px; }
  .bp3-button:empty::before,
  .bp3-button > :last-child{
    margin-right:0; }
  .bp3-button:empty{
    padding:0 !important; }
  .bp3-button:disabled, .bp3-button.bp3-disabled{
    cursor:not-allowed; }
  .bp3-button.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-button.bp3-align-right,
  .bp3-align-right .bp3-button{
    text-align:right; }
  .bp3-button.bp3-align-left,
  .bp3-align-left .bp3-button{
    text-align:left; }
  .bp3-button:not([class*="bp3-intent-"]){
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    color:#182026; }
    .bp3-button:not([class*="bp3-intent-"]):hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
      background-clip:padding-box;
      background-color:#ebf1f5; }
    .bp3-button:not([class*="bp3-intent-"]):active, .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#d8e1e8;
      background-image:none; }
    .bp3-button:not([class*="bp3-intent-"]):disabled, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled{
      outline:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(206, 217, 224, 0.5);
      background-image:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active, .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active:hover, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active:hover{
        background:rgba(206, 217, 224, 0.7); }
  .bp3-button.bp3-intent-primary{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-primary:hover, .bp3-button.bp3-intent-primary:active, .bp3-button.bp3-intent-primary.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-primary:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#106ba3; }
    .bp3-button.bp3-intent-primary:active, .bp3-button.bp3-intent-primary.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#0e5a8a;
      background-image:none; }
    .bp3-button.bp3-intent-primary:disabled, .bp3-button.bp3-intent-primary.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(19, 124, 189, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-success{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#0f9960;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-success:hover, .bp3-button.bp3-intent-success:active, .bp3-button.bp3-intent-success.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-success:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#0d8050; }
    .bp3-button.bp3-intent-success:active, .bp3-button.bp3-intent-success.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#0a6640;
      background-image:none; }
    .bp3-button.bp3-intent-success:disabled, .bp3-button.bp3-intent-success.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(15, 153, 96, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-warning{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#d9822b;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-warning:hover, .bp3-button.bp3-intent-warning:active, .bp3-button.bp3-intent-warning.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-warning:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#bf7326; }
    .bp3-button.bp3-intent-warning:active, .bp3-button.bp3-intent-warning.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#a66321;
      background-image:none; }
    .bp3-button.bp3-intent-warning:disabled, .bp3-button.bp3-intent-warning.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(217, 130, 43, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-danger{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#db3737;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-danger:hover, .bp3-button.bp3-intent-danger:active, .bp3-button.bp3-intent-danger.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-danger:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#c23030; }
    .bp3-button.bp3-intent-danger:active, .bp3-button.bp3-intent-danger.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#a82a2a;
      background-image:none; }
    .bp3-button.bp3-intent-danger:disabled, .bp3-button.bp3-intent-danger.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(219, 55, 55, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button[class*="bp3-intent-"] .bp3-button-spinner .bp3-spinner-head{
    stroke:#ffffff; }
  .bp3-button.bp3-large,
  .bp3-large .bp3-button{
    min-width:40px;
    min-height:40px;
    padding:5px 15px;
    font-size:16px; }
    .bp3-button.bp3-large::before,
    .bp3-button.bp3-large > *,
    .bp3-large .bp3-button::before,
    .bp3-large .bp3-button > *{
      margin-right:10px; }
    .bp3-button.bp3-large:empty::before,
    .bp3-button.bp3-large > :last-child,
    .bp3-large .bp3-button:empty::before,
    .bp3-large .bp3-button > :last-child{
      margin-right:0; }
  .bp3-button.bp3-small,
  .bp3-small .bp3-button{
    min-width:24px;
    min-height:24px;
    padding:0 7px; }
  .bp3-button.bp3-loading{
    position:relative; }
    .bp3-button.bp3-loading[class*="bp3-icon-"]::before{
      visibility:hidden; }
    .bp3-button.bp3-loading .bp3-button-spinner{
      position:absolute;
      margin:0; }
    .bp3-button.bp3-loading > :not(.bp3-button-spinner){
      visibility:hidden; }
  .bp3-button[class*="bp3-icon-"]::before{
    line-height:1;
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-weight:400;
    font-style:normal;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    color:#5c7080; }
  .bp3-button .bp3-icon, .bp3-button .bp3-icon-standard, .bp3-button .bp3-icon-large{
    color:#5c7080; }
    .bp3-button .bp3-icon.bp3-align-right, .bp3-button .bp3-icon-standard.bp3-align-right, .bp3-button .bp3-icon-large.bp3-align-right{
      margin-left:7px; }
  .bp3-button .bp3-icon:first-child:last-child,
  .bp3-button .bp3-spinner + .bp3-icon:last-child{
    margin:0 -7px; }
  .bp3-dark .bp3-button:not([class*="bp3-intent-"]){
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#394b59;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
    color:#f5f8fa; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):hover, .bp3-dark .bp3-button:not([class*="bp3-intent-"]):active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      color:#f5f8fa; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):hover{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#30404d; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#202b33;
      background-image:none; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):disabled, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(57, 75, 89, 0.5);
      background-image:none;
      color:rgba(167, 182, 194, 0.6); }
      .bp3-dark .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active{
        background:rgba(57, 75, 89, 0.7); }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-button-spinner .bp3-spinner-head{
      background:rgba(16, 22, 26, 0.5);
      stroke:#8a9ba8; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"])[class*="bp3-icon-"]::before{
      color:#a7b6c2; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon, .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon-standard, .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon-large{
      color:#a7b6c2; }
  .bp3-dark .bp3-button[class*="bp3-intent-"]{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:hover{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:active, .bp3-dark .bp3-button[class*="bp3-intent-"].bp3-active{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:disabled, .bp3-dark .bp3-button[class*="bp3-intent-"].bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background-image:none;
      color:rgba(255, 255, 255, 0.3); }
    .bp3-dark .bp3-button[class*="bp3-intent-"] .bp3-button-spinner .bp3-spinner-head{
      stroke:#8a9ba8; }
  .bp3-button:disabled::before,
  .bp3-button:disabled .bp3-icon, .bp3-button:disabled .bp3-icon-standard, .bp3-button:disabled .bp3-icon-large, .bp3-button.bp3-disabled::before,
  .bp3-button.bp3-disabled .bp3-icon, .bp3-button.bp3-disabled .bp3-icon-standard, .bp3-button.bp3-disabled .bp3-icon-large, .bp3-button[class*="bp3-intent-"]::before,
  .bp3-button[class*="bp3-intent-"] .bp3-icon, .bp3-button[class*="bp3-intent-"] .bp3-icon-standard, .bp3-button[class*="bp3-intent-"] .bp3-icon-large{
    color:inherit !important; }
  .bp3-button.bp3-minimal{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none; }
    .bp3-button.bp3-minimal:hover{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(167, 182, 194, 0.3);
      text-decoration:none;
      color:#182026; }
    .bp3-button.bp3-minimal:active, .bp3-button.bp3-minimal.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(115, 134, 148, 0.3);
      color:#182026; }
    .bp3-button.bp3-minimal:disabled, .bp3-button.bp3-minimal:disabled:hover, .bp3-button.bp3-minimal.bp3-disabled, .bp3-button.bp3-minimal.bp3-disabled:hover{
      background:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-button.bp3-minimal:disabled.bp3-active, .bp3-button.bp3-minimal:disabled:hover.bp3-active, .bp3-button.bp3-minimal.bp3-disabled.bp3-active, .bp3-button.bp3-minimal.bp3-disabled:hover.bp3-active{
        background:rgba(115, 134, 148, 0.3); }
    .bp3-dark .bp3-button.bp3-minimal{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:inherit; }
      .bp3-dark .bp3-button.bp3-minimal:hover, .bp3-dark .bp3-button.bp3-minimal:active, .bp3-dark .bp3-button.bp3-minimal.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none; }
      .bp3-dark .bp3-button.bp3-minimal:hover{
        background:rgba(138, 155, 168, 0.15); }
      .bp3-dark .bp3-button.bp3-minimal:active, .bp3-dark .bp3-button.bp3-minimal.bp3-active{
        background:rgba(138, 155, 168, 0.3);
        color:#f5f8fa; }
      .bp3-dark .bp3-button.bp3-minimal:disabled, .bp3-dark .bp3-button.bp3-minimal:disabled:hover, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled:hover{
        background:none;
        cursor:not-allowed;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-button.bp3-minimal:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal:disabled:hover.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled:hover.bp3-active{
          background:rgba(138, 155, 168, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-primary{
      color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:hover, .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.15);
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:disabled, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(16, 107, 163, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-primary:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
        stroke:#106ba3; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary{
        color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:hover{
          background:rgba(19, 124, 189, 0.2);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
          background:rgba(19, 124, 189, 0.3);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled{
          background:none;
          color:rgba(72, 175, 240, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled.bp3-active{
            background:rgba(19, 124, 189, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-success{
      color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:hover, .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.15);
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:disabled, .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(13, 128, 80, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-success:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
        stroke:#0d8050; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success{
        color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:hover{
          background:rgba(15, 153, 96, 0.2);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
          background:rgba(15, 153, 96, 0.3);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled{
          background:none;
          color:rgba(61, 204, 145, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled.bp3-active{
            background:rgba(15, 153, 96, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-warning{
      color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:hover, .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.15);
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:disabled, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(191, 115, 38, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-warning:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
        stroke:#bf7326; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning{
        color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:hover{
          background:rgba(217, 130, 43, 0.2);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
          background:rgba(217, 130, 43, 0.3);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled{
          background:none;
          color:rgba(255, 179, 102, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled.bp3-active{
            background:rgba(217, 130, 43, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-danger{
      color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:hover, .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.15);
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:disabled, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(194, 48, 48, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-danger:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
        stroke:#c23030; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger{
        color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:hover{
          background:rgba(219, 55, 55, 0.2);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
          background:rgba(219, 55, 55, 0.3);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled{
          background:none;
          color:rgba(255, 115, 115, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled.bp3-active{
            background:rgba(219, 55, 55, 0.3); }

a.bp3-button{
  text-align:center;
  text-decoration:none;
  -webkit-transition:none;
  transition:none; }
  a.bp3-button, a.bp3-button:hover, a.bp3-button:active{
    color:#182026; }
  a.bp3-button.bp3-disabled{
    color:rgba(92, 112, 128, 0.6); }

.bp3-button-text{
  -webkit-box-flex:0;
      -ms-flex:0 1 auto;
          flex:0 1 auto; }

.bp3-button.bp3-align-left .bp3-button-text, .bp3-button.bp3-align-right .bp3-button-text,
.bp3-button-group.bp3-align-left .bp3-button-text,
.bp3-button-group.bp3-align-right .bp3-button-text{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto; }
.bp3-button-group{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex; }
  .bp3-button-group .bp3-button{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    position:relative;
    z-index:4; }
    .bp3-button-group .bp3-button:focus{
      z-index:5; }
    .bp3-button-group .bp3-button:hover{
      z-index:6; }
    .bp3-button-group .bp3-button:active, .bp3-button-group .bp3-button.bp3-active{
      z-index:7; }
    .bp3-button-group .bp3-button:disabled, .bp3-button-group .bp3-button.bp3-disabled{
      z-index:3; }
    .bp3-button-group .bp3-button[class*="bp3-intent-"]{
      z-index:9; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:focus{
        z-index:10; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:hover{
        z-index:11; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:active, .bp3-button-group .bp3-button[class*="bp3-intent-"].bp3-active{
        z-index:12; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:disabled, .bp3-button-group .bp3-button[class*="bp3-intent-"].bp3-disabled{
        z-index:8; }
  .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:first-child) .bp3-button,
  .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:first-child){
    border-top-left-radius:0;
    border-bottom-left-radius:0; }
  .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:last-child){
    margin-right:-1px;
    border-top-right-radius:0;
    border-bottom-right-radius:0; }
  .bp3-button-group.bp3-minimal .bp3-button{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none; }
    .bp3-button-group.bp3-minimal .bp3-button:hover{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(167, 182, 194, 0.3);
      text-decoration:none;
      color:#182026; }
    .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(115, 134, 148, 0.3);
      color:#182026; }
    .bp3-button-group.bp3-minimal .bp3-button:disabled, .bp3-button-group.bp3-minimal .bp3-button:disabled:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover{
      background:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-button-group.bp3-minimal .bp3-button:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button:disabled:hover.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover.bp3-active{
        background:rgba(115, 134, 148, 0.3); }
    .bp3-dark .bp3-button-group.bp3-minimal .bp3-button{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:inherit; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:hover, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:hover{
        background:rgba(138, 155, 168, 0.15); }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
        background:rgba(138, 155, 168, 0.3);
        color:#f5f8fa; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled:hover, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover{
        background:none;
        cursor:not-allowed;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled:hover.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover.bp3-active{
          background:rgba(138, 155, 168, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary{
      color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.15);
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(16, 107, 163, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
        stroke:#106ba3; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary{
        color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover{
          background:rgba(19, 124, 189, 0.2);
          color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
          background:rgba(19, 124, 189, 0.3);
          color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled{
          background:none;
          color:rgba(72, 175, 240, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled.bp3-active{
            background:rgba(19, 124, 189, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success{
      color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.15);
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(13, 128, 80, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
        stroke:#0d8050; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success{
        color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover{
          background:rgba(15, 153, 96, 0.2);
          color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
          background:rgba(15, 153, 96, 0.3);
          color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled{
          background:none;
          color:rgba(61, 204, 145, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled.bp3-active{
            background:rgba(15, 153, 96, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning{
      color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.15);
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(191, 115, 38, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
        stroke:#bf7326; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning{
        color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover{
          background:rgba(217, 130, 43, 0.2);
          color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
          background:rgba(217, 130, 43, 0.3);
          color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled{
          background:none;
          color:rgba(255, 179, 102, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled.bp3-active{
            background:rgba(217, 130, 43, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger{
      color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.15);
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(194, 48, 48, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
        stroke:#c23030; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger{
        color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover{
          background:rgba(219, 55, 55, 0.2);
          color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
          background:rgba(219, 55, 55, 0.3);
          color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled{
          background:none;
          color:rgba(255, 115, 115, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled.bp3-active{
            background:rgba(219, 55, 55, 0.3); }
  .bp3-button-group .bp3-popover-wrapper,
  .bp3-button-group .bp3-popover-target{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-button-group.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-button-group .bp3-button.bp3-fill,
  .bp3-button-group.bp3-fill .bp3-button:not(.bp3-fixed){
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-button-group.bp3-vertical{
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column;
    -webkit-box-align:stretch;
        -ms-flex-align:stretch;
            align-items:stretch;
    vertical-align:top; }
    .bp3-button-group.bp3-vertical.bp3-fill{
      width:unset;
      height:100%; }
    .bp3-button-group.bp3-vertical .bp3-button{
      margin-right:0 !important;
      width:100%; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:first-child .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:first-child{
      border-radius:3px 3px 0 0; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:last-child .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:last-child{
      border-radius:0 0 3px 3px; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:not(:last-child){
      margin-bottom:-1px; }
  .bp3-button-group.bp3-align-left .bp3-button{
    text-align:left; }
  .bp3-dark .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-dark .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:last-child){
    margin-right:1px; }
  .bp3-dark .bp3-button-group.bp3-vertical > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-dark .bp3-button-group.bp3-vertical > .bp3-button:not(:last-child){
    margin-bottom:1px; }
.bp3-callout{
  line-height:1.5;
  font-size:14px;
  position:relative;
  border-radius:3px;
  background-color:rgba(138, 155, 168, 0.15);
  width:100%;
  padding:10px 12px 9px; }
  .bp3-callout[class*="bp3-icon-"]{
    padding-left:40px; }
    .bp3-callout[class*="bp3-icon-"]::before{
      line-height:1;
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-weight:400;
      font-style:normal;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased;
      position:absolute;
      top:10px;
      left:10px;
      color:#5c7080; }
  .bp3-callout.bp3-callout-icon{
    padding-left:40px; }
    .bp3-callout.bp3-callout-icon > .bp3-icon:first-child{
      position:absolute;
      top:10px;
      left:10px;
      color:#5c7080; }
  .bp3-callout .bp3-heading{
    margin-top:0;
    margin-bottom:5px;
    line-height:20px; }
    .bp3-callout .bp3-heading:last-child{
      margin-bottom:0; }
  .bp3-dark .bp3-callout{
    background-color:rgba(138, 155, 168, 0.2); }
    .bp3-dark .bp3-callout[class*="bp3-icon-"]::before{
      color:#a7b6c2; }
  .bp3-callout.bp3-intent-primary{
    background-color:rgba(19, 124, 189, 0.15); }
    .bp3-callout.bp3-intent-primary[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-primary > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-primary .bp3-heading{
      color:#106ba3; }
    .bp3-dark .bp3-callout.bp3-intent-primary{
      background-color:rgba(19, 124, 189, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-primary[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-primary > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-primary .bp3-heading{
        color:#48aff0; }
  .bp3-callout.bp3-intent-success{
    background-color:rgba(15, 153, 96, 0.15); }
    .bp3-callout.bp3-intent-success[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-success > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-success .bp3-heading{
      color:#0d8050; }
    .bp3-dark .bp3-callout.bp3-intent-success{
      background-color:rgba(15, 153, 96, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-success[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-success > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-success .bp3-heading{
        color:#3dcc91; }
  .bp3-callout.bp3-intent-warning{
    background-color:rgba(217, 130, 43, 0.15); }
    .bp3-callout.bp3-intent-warning[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-warning > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-warning .bp3-heading{
      color:#bf7326; }
    .bp3-dark .bp3-callout.bp3-intent-warning{
      background-color:rgba(217, 130, 43, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-warning[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-warning > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-warning .bp3-heading{
        color:#ffb366; }
  .bp3-callout.bp3-intent-danger{
    background-color:rgba(219, 55, 55, 0.15); }
    .bp3-callout.bp3-intent-danger[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-danger > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-danger .bp3-heading{
      color:#c23030; }
    .bp3-dark .bp3-callout.bp3-intent-danger{
      background-color:rgba(219, 55, 55, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-danger[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-danger > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-danger .bp3-heading{
        color:#ff7373; }
  .bp3-running-text .bp3-callout{
    margin:20px 0; }
.bp3-card{
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
  background-color:#ffffff;
  padding:20px;
  -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-card.bp3-dark,
  .bp3-dark .bp3-card{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
    background-color:#30404d; }

.bp3-elevation-0{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0); }
  .bp3-elevation-0.bp3-dark,
  .bp3-dark .bp3-elevation-0{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0); }

.bp3-elevation-1{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-1.bp3-dark,
  .bp3-dark .bp3-elevation-1{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-elevation-2{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 1px 1px rgba(16, 22, 26, 0.2), 0 2px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 1px 1px rgba(16, 22, 26, 0.2), 0 2px 6px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-2.bp3-dark,
  .bp3-dark .bp3-elevation-2{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.4), 0 2px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.4), 0 2px 6px rgba(16, 22, 26, 0.4); }

.bp3-elevation-3{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-3.bp3-dark,
  .bp3-dark .bp3-elevation-3{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }

.bp3-elevation-4{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-4.bp3-dark,
  .bp3-dark .bp3-elevation-4{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4); }

.bp3-card.bp3-interactive:hover{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  cursor:pointer; }
  .bp3-card.bp3-interactive:hover.bp3-dark,
  .bp3-dark .bp3-card.bp3-interactive:hover{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }

.bp3-card.bp3-interactive:active{
  opacity:0.9;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  -webkit-transition-duration:0;
          transition-duration:0; }
  .bp3-card.bp3-interactive:active.bp3-dark,
  .bp3-dark .bp3-card.bp3-interactive:active{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-collapse{
  height:0;
  overflow-y:hidden;
  -webkit-transition:height 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:height 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-collapse .bp3-collapse-body{
    -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-collapse .bp3-collapse-body[aria-hidden="true"]{
      display:none; }

.bp3-context-menu .bp3-popover-target{
  display:block; }

.bp3-context-menu-popover-target{
  position:fixed; }

.bp3-divider{
  margin:5px;
  border-right:1px solid rgba(16, 22, 26, 0.15);
  border-bottom:1px solid rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-divider{
    border-color:rgba(16, 22, 26, 0.4); }
.bp3-dialog-container{
  opacity:1;
  -webkit-transform:scale(1);
          transform:scale(1);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  width:100%;
  min-height:100%;
  pointer-events:none;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-dialog-container.bp3-overlay-enter > .bp3-dialog, .bp3-dialog-container.bp3-overlay-appear > .bp3-dialog{
    opacity:0;
    -webkit-transform:scale(0.5);
            transform:scale(0.5); }
  .bp3-dialog-container.bp3-overlay-enter-active > .bp3-dialog, .bp3-dialog-container.bp3-overlay-appear-active > .bp3-dialog{
    opacity:1;
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-property:opacity, -webkit-transform;
    transition-property:opacity, -webkit-transform;
    transition-property:opacity, transform;
    transition-property:opacity, transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-dialog-container.bp3-overlay-exit > .bp3-dialog{
    opacity:1;
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-dialog-container.bp3-overlay-exit-active > .bp3-dialog{
    opacity:0;
    -webkit-transform:scale(0.5);
            transform:scale(0.5);
    -webkit-transition-property:opacity, -webkit-transform;
    transition-property:opacity, -webkit-transform;
    transition-property:opacity, transform;
    transition-property:opacity, transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }

.bp3-dialog{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:30px 0;
  border-radius:6px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  background:#ebf1f5;
  width:500px;
  padding-bottom:20px;
  pointer-events:all;
  -webkit-user-select:text;
     -moz-user-select:text;
      -ms-user-select:text;
          user-select:text; }
  .bp3-dialog:focus{
    outline:0; }
  .bp3-dialog.bp3-dark,
  .bp3-dark .bp3-dialog{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    background:#293742;
    color:#f5f8fa; }

.bp3-dialog-header{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  border-radius:6px 6px 0 0;
  -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
  background:#ffffff;
  min-height:40px;
  padding-right:5px;
  padding-left:20px; }
  .bp3-dialog-header .bp3-icon-large,
  .bp3-dialog-header .bp3-icon{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    margin-right:10px;
    color:#5c7080; }
  .bp3-dialog-header .bp3-heading{
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    margin:0;
    line-height:inherit; }
    .bp3-dialog-header .bp3-heading:last-child{
      margin-right:20px; }
  .bp3-dark .bp3-dialog-header{
    -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
    background:#30404d; }
    .bp3-dark .bp3-dialog-header .bp3-icon-large,
    .bp3-dark .bp3-dialog-header .bp3-icon{
      color:#a7b6c2; }

.bp3-dialog-body{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  margin:20px;
  line-height:18px; }

.bp3-dialog-footer{
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  margin:0 20px; }

.bp3-dialog-footer-actions{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-pack:end;
      -ms-flex-pack:end;
          justify-content:flex-end; }
  .bp3-dialog-footer-actions .bp3-button{
    margin-left:10px; }
.bp3-drawer{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:0;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  padding:0; }
  .bp3-drawer:focus{
    outline:0; }
  .bp3-drawer.bp3-position-top{
    top:0;
    right:0;
    left:0;
    height:50%; }
    .bp3-drawer.bp3-position-top.bp3-overlay-enter, .bp3-drawer.bp3-position-top.bp3-overlay-appear{
      -webkit-transform:translateY(-100%);
              transform:translateY(-100%); }
    .bp3-drawer.bp3-position-top.bp3-overlay-enter-active, .bp3-drawer.bp3-position-top.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-top.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer.bp3-position-top.bp3-overlay-exit-active{
      -webkit-transform:translateY(-100%);
              transform:translateY(-100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-position-bottom{
    right:0;
    bottom:0;
    left:0;
    height:50%; }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-enter, .bp3-drawer.bp3-position-bottom.bp3-overlay-appear{
      -webkit-transform:translateY(100%);
              transform:translateY(100%); }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-enter-active, .bp3-drawer.bp3-position-bottom.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-exit-active{
      -webkit-transform:translateY(100%);
              transform:translateY(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-position-left{
    top:0;
    bottom:0;
    left:0;
    width:50%; }
    .bp3-drawer.bp3-position-left.bp3-overlay-enter, .bp3-drawer.bp3-position-left.bp3-overlay-appear{
      -webkit-transform:translateX(-100%);
              transform:translateX(-100%); }
    .bp3-drawer.bp3-position-left.bp3-overlay-enter-active, .bp3-drawer.bp3-position-left.bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-left.bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer.bp3-position-left.bp3-overlay-exit-active{
      -webkit-transform:translateX(-100%);
              transform:translateX(-100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-position-right{
    top:0;
    right:0;
    bottom:0;
    width:50%; }
    .bp3-drawer.bp3-position-right.bp3-overlay-enter, .bp3-drawer.bp3-position-right.bp3-overlay-appear{
      -webkit-transform:translateX(100%);
              transform:translateX(100%); }
    .bp3-drawer.bp3-position-right.bp3-overlay-enter-active, .bp3-drawer.bp3-position-right.bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-right.bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer.bp3-position-right.bp3-overlay-exit-active{
      -webkit-transform:translateX(100%);
              transform:translateX(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
  .bp3-position-right):not(.bp3-vertical){
    top:0;
    right:0;
    bottom:0;
    width:50%; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-enter, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-appear{
      -webkit-transform:translateX(100%);
              transform:translateX(100%); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-enter-active, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-exit-active{
      -webkit-transform:translateX(100%);
              transform:translateX(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
  .bp3-position-right).bp3-vertical{
    right:0;
    bottom:0;
    left:0;
    height:50%; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-enter, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-appear{
      -webkit-transform:translateY(100%);
              transform:translateY(100%); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-enter-active, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-exit-active{
      -webkit-transform:translateY(100%);
              transform:translateY(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-dark,
  .bp3-dark .bp3-drawer{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    background:#30404d;
    color:#f5f8fa; }

.bp3-drawer-header{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  position:relative;
  border-radius:0;
  -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
  min-height:40px;
  padding:5px;
  padding-left:20px; }
  .bp3-drawer-header .bp3-icon-large,
  .bp3-drawer-header .bp3-icon{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    margin-right:10px;
    color:#5c7080; }
  .bp3-drawer-header .bp3-heading{
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    margin:0;
    line-height:inherit; }
    .bp3-drawer-header .bp3-heading:last-child{
      margin-right:20px; }
  .bp3-dark .bp3-drawer-header{
    -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:0 1px 0 rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-drawer-header .bp3-icon-large,
    .bp3-dark .bp3-drawer-header .bp3-icon{
      color:#a7b6c2; }

.bp3-drawer-body{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  overflow:auto;
  line-height:18px; }

.bp3-drawer-footer{
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  position:relative;
  -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
  padding:10px 20px; }
  .bp3-dark .bp3-drawer-footer{
    -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.4); }
.bp3-editable-text{
  display:inline-block;
  position:relative;
  cursor:text;
  max-width:100%;
  vertical-align:top;
  white-space:nowrap; }
  .bp3-editable-text::before{
    position:absolute;
    top:-3px;
    right:-3px;
    bottom:-3px;
    left:-3px;
    border-radius:3px;
    content:"";
    -webkit-transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-editable-text:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-editable-text.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
    background-color:#ffffff; }
  .bp3-editable-text.bp3-disabled::before{
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-editable-text.bp3-intent-primary .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-primary .bp3-editable-text-content{
    color:#137cbd; }
  .bp3-editable-text.bp3-intent-primary:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(19, 124, 189, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(19, 124, 189, 0.4); }
  .bp3-editable-text.bp3-intent-primary.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-success .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-success .bp3-editable-text-content{
    color:#0f9960; }
  .bp3-editable-text.bp3-intent-success:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px rgba(15, 153, 96, 0.4);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px rgba(15, 153, 96, 0.4); }
  .bp3-editable-text.bp3-intent-success.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-warning .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-warning .bp3-editable-text-content{
    color:#d9822b; }
  .bp3-editable-text.bp3-intent-warning:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px rgba(217, 130, 43, 0.4);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px rgba(217, 130, 43, 0.4); }
  .bp3-editable-text.bp3-intent-warning.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-danger .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-danger .bp3-editable-text-content{
    color:#db3737; }
  .bp3-editable-text.bp3-intent-danger:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px rgba(219, 55, 55, 0.4);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px rgba(219, 55, 55, 0.4); }
  .bp3-editable-text.bp3-intent-danger.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-editable-text:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(255, 255, 255, 0.15);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(255, 255, 255, 0.15); }
  .bp3-dark .bp3-editable-text.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background-color:rgba(16, 22, 26, 0.3); }
  .bp3-dark .bp3-editable-text.bp3-disabled::before{
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-dark .bp3-editable-text.bp3-intent-primary .bp3-editable-text-content{
    color:#48aff0; }
  .bp3-dark .bp3-editable-text.bp3-intent-primary:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(72, 175, 240, 0), 0 0 0 0 rgba(72, 175, 240, 0), inset 0 0 0 1px rgba(72, 175, 240, 0.4);
            box-shadow:0 0 0 0 rgba(72, 175, 240, 0), 0 0 0 0 rgba(72, 175, 240, 0), inset 0 0 0 1px rgba(72, 175, 240, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-primary.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #48aff0, 0 0 0 3px rgba(72, 175, 240, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #48aff0, 0 0 0 3px rgba(72, 175, 240, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-success .bp3-editable-text-content{
    color:#3dcc91; }
  .bp3-dark .bp3-editable-text.bp3-intent-success:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(61, 204, 145, 0), 0 0 0 0 rgba(61, 204, 145, 0), inset 0 0 0 1px rgba(61, 204, 145, 0.4);
            box-shadow:0 0 0 0 rgba(61, 204, 145, 0), 0 0 0 0 rgba(61, 204, 145, 0), inset 0 0 0 1px rgba(61, 204, 145, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-success.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #3dcc91, 0 0 0 3px rgba(61, 204, 145, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #3dcc91, 0 0 0 3px rgba(61, 204, 145, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-warning .bp3-editable-text-content{
    color:#ffb366; }
  .bp3-dark .bp3-editable-text.bp3-intent-warning:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(255, 179, 102, 0), 0 0 0 0 rgba(255, 179, 102, 0), inset 0 0 0 1px rgba(255, 179, 102, 0.4);
            box-shadow:0 0 0 0 rgba(255, 179, 102, 0), 0 0 0 0 rgba(255, 179, 102, 0), inset 0 0 0 1px rgba(255, 179, 102, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-warning.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #ffb366, 0 0 0 3px rgba(255, 179, 102, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #ffb366, 0 0 0 3px rgba(255, 179, 102, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-danger .bp3-editable-text-content{
    color:#ff7373; }
  .bp3-dark .bp3-editable-text.bp3-intent-danger:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(255, 115, 115, 0), 0 0 0 0 rgba(255, 115, 115, 0), inset 0 0 0 1px rgba(255, 115, 115, 0.4);
            box-shadow:0 0 0 0 rgba(255, 115, 115, 0), 0 0 0 0 rgba(255, 115, 115, 0), inset 0 0 0 1px rgba(255, 115, 115, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-danger.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #ff7373, 0 0 0 3px rgba(255, 115, 115, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #ff7373, 0 0 0 3px rgba(255, 115, 115, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-editable-text-input,
.bp3-editable-text-content{
  display:inherit;
  position:relative;
  min-width:inherit;
  max-width:inherit;
  vertical-align:top;
  text-transform:inherit;
  letter-spacing:inherit;
  color:inherit;
  font:inherit;
  resize:none; }

.bp3-editable-text-input{
  border:none;
  -webkit-box-shadow:none;
          box-shadow:none;
  background:none;
  width:100%;
  padding:0;
  white-space:pre-wrap; }
  .bp3-editable-text-input::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input:focus{
    outline:none; }
  .bp3-editable-text-input::-ms-clear{
    display:none; }

.bp3-editable-text-content{
  overflow:hidden;
  padding-right:2px;
  text-overflow:ellipsis;
  white-space:pre; }
  .bp3-editable-text-editing > .bp3-editable-text-content{
    position:absolute;
    left:0;
    visibility:hidden; }
  .bp3-editable-text-placeholder > .bp3-editable-text-content{
    color:rgba(92, 112, 128, 0.6); }
    .bp3-dark .bp3-editable-text-placeholder > .bp3-editable-text-content{
      color:rgba(167, 182, 194, 0.6); }

.bp3-editable-text.bp3-multiline{
  display:block; }
  .bp3-editable-text.bp3-multiline .bp3-editable-text-content{
    overflow:auto;
    white-space:pre-wrap;
    word-wrap:break-word; }
.bp3-control-group{
  -webkit-transform:translateZ(0);
          transform:translateZ(0);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:stretch;
      -ms-flex-align:stretch;
          align-items:stretch; }
  .bp3-control-group > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-control-group > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-control-group .bp3-button,
  .bp3-control-group .bp3-html-select,
  .bp3-control-group .bp3-input,
  .bp3-control-group .bp3-select{
    position:relative; }
  .bp3-control-group .bp3-input{
    z-index:2;
    border-radius:inherit; }
    .bp3-control-group .bp3-input:focus{
      z-index:14;
      border-radius:3px; }
    .bp3-control-group .bp3-input[class*="bp3-intent"]{
      z-index:13; }
      .bp3-control-group .bp3-input[class*="bp3-intent"]:focus{
        z-index:15; }
    .bp3-control-group .bp3-input[readonly], .bp3-control-group .bp3-input:disabled, .bp3-control-group .bp3-input.bp3-disabled{
      z-index:1; }
  .bp3-control-group .bp3-input-group[class*="bp3-intent"] .bp3-input{
    z-index:13; }
    .bp3-control-group .bp3-input-group[class*="bp3-intent"] .bp3-input:focus{
      z-index:15; }
  .bp3-control-group .bp3-button,
  .bp3-control-group .bp3-html-select select,
  .bp3-control-group .bp3-select select{
    -webkit-transform:translateZ(0);
            transform:translateZ(0);
    z-index:4;
    border-radius:inherit; }
    .bp3-control-group .bp3-button:focus,
    .bp3-control-group .bp3-html-select select:focus,
    .bp3-control-group .bp3-select select:focus{
      z-index:5; }
    .bp3-control-group .bp3-button:hover,
    .bp3-control-group .bp3-html-select select:hover,
    .bp3-control-group .bp3-select select:hover{
      z-index:6; }
    .bp3-control-group .bp3-button:active,
    .bp3-control-group .bp3-html-select select:active,
    .bp3-control-group .bp3-select select:active{
      z-index:7; }
    .bp3-control-group .bp3-button[readonly], .bp3-control-group .bp3-button:disabled, .bp3-control-group .bp3-button.bp3-disabled,
    .bp3-control-group .bp3-html-select select[readonly],
    .bp3-control-group .bp3-html-select select:disabled,
    .bp3-control-group .bp3-html-select select.bp3-disabled,
    .bp3-control-group .bp3-select select[readonly],
    .bp3-control-group .bp3-select select:disabled,
    .bp3-control-group .bp3-select select.bp3-disabled{
      z-index:3; }
    .bp3-control-group .bp3-button[class*="bp3-intent"],
    .bp3-control-group .bp3-html-select select[class*="bp3-intent"],
    .bp3-control-group .bp3-select select[class*="bp3-intent"]{
      z-index:9; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:focus,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:focus,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:focus{
        z-index:10; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:hover,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:hover,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:hover{
        z-index:11; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:active,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:active,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:active{
        z-index:12; }
      .bp3-control-group .bp3-button[class*="bp3-intent"][readonly], .bp3-control-group .bp3-button[class*="bp3-intent"]:disabled, .bp3-control-group .bp3-button[class*="bp3-intent"].bp3-disabled,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"][readonly],
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:disabled,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"].bp3-disabled,
      .bp3-control-group .bp3-select select[class*="bp3-intent"][readonly],
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:disabled,
      .bp3-control-group .bp3-select select[class*="bp3-intent"].bp3-disabled{
        z-index:8; }
  .bp3-control-group .bp3-input-group > .bp3-icon,
  .bp3-control-group .bp3-input-group > .bp3-button,
  .bp3-control-group .bp3-input-group > .bp3-input-action{
    z-index:16; }
  .bp3-control-group .bp3-select::after,
  .bp3-control-group .bp3-html-select::after,
  .bp3-control-group .bp3-select > .bp3-icon,
  .bp3-control-group .bp3-html-select > .bp3-icon{
    z-index:17; }
  .bp3-control-group:not(.bp3-vertical) > *{
    margin-right:-1px; }
  .bp3-dark .bp3-control-group:not(.bp3-vertical) > *{
    margin-right:0; }
  .bp3-dark .bp3-control-group:not(.bp3-vertical) > .bp3-button + .bp3-button{
    margin-left:1px; }
  .bp3-control-group .bp3-popover-wrapper,
  .bp3-control-group .bp3-popover-target{
    border-radius:inherit; }
  .bp3-control-group > :first-child{
    border-radius:3px 0 0 3px; }
  .bp3-control-group > :last-child{
    margin-right:0;
    border-radius:0 3px 3px 0; }
  .bp3-control-group > :only-child{
    margin-right:0;
    border-radius:3px; }
  .bp3-control-group .bp3-input-group .bp3-button{
    border-radius:3px; }
  .bp3-control-group > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-control-group.bp3-fill > *:not(.bp3-fixed){
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-control-group.bp3-vertical{
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column; }
    .bp3-control-group.bp3-vertical > *{
      margin-top:-1px; }
    .bp3-control-group.bp3-vertical > :first-child{
      margin-top:0;
      border-radius:3px 3px 0 0; }
    .bp3-control-group.bp3-vertical > :last-child{
      border-radius:0 0 3px 3px; }
.bp3-control{
  display:block;
  position:relative;
  margin-bottom:10px;
  cursor:pointer;
  text-transform:none; }
  .bp3-control input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
  .bp3-control:hover input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#106ba3; }
  .bp3-control input:not(:disabled):active:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background:#0e5a8a; }
  .bp3-control input:disabled:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(19, 124, 189, 0.5); }
  .bp3-dark .bp3-control input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control:hover input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#106ba3; }
  .bp3-dark .bp3-control input:not(:disabled):active:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#0e5a8a; }
  .bp3-dark .bp3-control input:disabled:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(14, 90, 138, 0.5); }
  .bp3-control:not(.bp3-align-right){
    padding-left:26px; }
    .bp3-control:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-26px; }
  .bp3-control.bp3-align-right{
    padding-right:26px; }
    .bp3-control.bp3-align-right .bp3-control-indicator{
      margin-right:-26px; }
  .bp3-control.bp3-disabled{
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-control.bp3-inline{
    display:inline-block;
    margin-right:20px; }
  .bp3-control input{
    position:absolute;
    top:0;
    left:0;
    opacity:0;
    z-index:-1; }
  .bp3-control .bp3-control-indicator{
    display:inline-block;
    position:relative;
    margin-top:-3px;
    margin-right:10px;
    border:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    cursor:pointer;
    width:1em;
    height:1em;
    vertical-align:middle;
    font-size:16px;
    -webkit-user-select:none;
       -moz-user-select:none;
        -ms-user-select:none;
            user-select:none; }
    .bp3-control .bp3-control-indicator::before{
      display:block;
      width:1em;
      height:1em;
      content:""; }
  .bp3-control:hover .bp3-control-indicator{
    background-color:#ebf1f5; }
  .bp3-control input:not(:disabled):active ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background:#d8e1e8; }
  .bp3-control input:disabled ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(206, 217, 224, 0.5);
    cursor:not-allowed; }
  .bp3-control input:focus ~ .bp3-control-indicator{
    outline:rgba(19, 124, 189, 0.6) auto 2px;
    outline-offset:2px;
    -moz-outline-radius:6px; }
  .bp3-control.bp3-align-right .bp3-control-indicator{
    float:right;
    margin-top:1px;
    margin-left:10px; }
  .bp3-control.bp3-large{
    font-size:16px; }
    .bp3-control.bp3-large:not(.bp3-align-right){
      padding-left:30px; }
      .bp3-control.bp3-large:not(.bp3-align-right) .bp3-control-indicator{
        margin-left:-30px; }
    .bp3-control.bp3-large.bp3-align-right{
      padding-right:30px; }
      .bp3-control.bp3-large.bp3-align-right .bp3-control-indicator{
        margin-right:-30px; }
    .bp3-control.bp3-large .bp3-control-indicator{
      font-size:20px; }
    .bp3-control.bp3-large.bp3-align-right .bp3-control-indicator{
      margin-top:0; }
  .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
  .bp3-control.bp3-checkbox:hover input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#106ba3; }
  .bp3-control.bp3-checkbox input:not(:disabled):active:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background:#0e5a8a; }
  .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(19, 124, 189, 0.5); }
  .bp3-dark .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-checkbox:hover input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#106ba3; }
  .bp3-dark .bp3-control.bp3-checkbox input:not(:disabled):active:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#0e5a8a; }
  .bp3-dark .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(14, 90, 138, 0.5); }
  .bp3-control.bp3-checkbox .bp3-control-indicator{
    border-radius:3px; }
  .bp3-control.bp3-checkbox input:checked ~ .bp3-control-indicator::before{
    background-image:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M12 5c-.28 0-.53.11-.71.29L7 9.59l-2.29-2.3a1.003 1.003 0 0 0-1.42 1.42l3 3c.18.18.43.29.71.29s.53-.11.71-.29l5-5A1.003 1.003 0 0 0 12 5z' fill='white'/%3e%3c/svg%3e"); }
  .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator::before{
    background-image:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M11 7H5c-.55 0-1 .45-1 1s.45 1 1 1h6c.55 0 1-.45 1-1s-.45-1-1-1z' fill='white'/%3e%3c/svg%3e"); }
  .bp3-control.bp3-radio .bp3-control-indicator{
    border-radius:50%; }
  .bp3-control.bp3-radio input:checked ~ .bp3-control-indicator::before{
    background-image:radial-gradient(#ffffff, #ffffff 28%, transparent 32%); }
  .bp3-control.bp3-radio input:checked:disabled ~ .bp3-control-indicator::before{
    opacity:0.5; }
  .bp3-control.bp3-radio input:focus ~ .bp3-control-indicator{
    -moz-outline-radius:16px; }
  .bp3-control.bp3-switch input ~ .bp3-control-indicator{
    background:rgba(167, 182, 194, 0.5); }
  .bp3-control.bp3-switch:hover input ~ .bp3-control-indicator{
    background:rgba(115, 134, 148, 0.5); }
  .bp3-control.bp3-switch input:not(:disabled):active ~ .bp3-control-indicator{
    background:rgba(92, 112, 128, 0.5); }
  .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator{
    background:rgba(206, 217, 224, 0.5); }
    .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator::before{
      background:rgba(255, 255, 255, 0.8); }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator{
    background:#137cbd; }
  .bp3-control.bp3-switch:hover input:checked ~ .bp3-control-indicator{
    background:#106ba3; }
  .bp3-control.bp3-switch input:checked:not(:disabled):active ~ .bp3-control-indicator{
    background:#0e5a8a; }
  .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator{
    background:rgba(19, 124, 189, 0.5); }
    .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator::before{
      background:rgba(255, 255, 255, 0.8); }
  .bp3-control.bp3-switch:not(.bp3-align-right){
    padding-left:38px; }
    .bp3-control.bp3-switch:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-38px; }
  .bp3-control.bp3-switch.bp3-align-right{
    padding-right:38px; }
    .bp3-control.bp3-switch.bp3-align-right .bp3-control-indicator{
      margin-right:-38px; }
  .bp3-control.bp3-switch .bp3-control-indicator{
    border:none;
    border-radius:1.75em;
    -webkit-box-shadow:none !important;
            box-shadow:none !important;
    width:auto;
    min-width:1.75em;
    -webkit-transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-control.bp3-switch .bp3-control-indicator::before{
      position:absolute;
      left:0;
      margin:2px;
      border-radius:50%;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
      background:#ffffff;
      width:calc(1em - 4px);
      height:calc(1em - 4px);
      -webkit-transition:left 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
      transition:left 100ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator::before{
    left:calc(100% - 1em); }
  .bp3-control.bp3-switch.bp3-large:not(.bp3-align-right){
    padding-left:45px; }
    .bp3-control.bp3-switch.bp3-large:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-45px; }
  .bp3-control.bp3-switch.bp3-large.bp3-align-right{
    padding-right:45px; }
    .bp3-control.bp3-switch.bp3-large.bp3-align-right .bp3-control-indicator{
      margin-right:-45px; }
  .bp3-dark .bp3-control.bp3-switch input ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.5); }
  .bp3-dark .bp3-control.bp3-switch:hover input ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.7); }
  .bp3-dark .bp3-control.bp3-switch input:not(:disabled):active ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.9); }
  .bp3-dark .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator{
    background:rgba(57, 75, 89, 0.5); }
    .bp3-dark .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator::before{
      background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator{
    background:#137cbd; }
  .bp3-dark .bp3-control.bp3-switch:hover input:checked ~ .bp3-control-indicator{
    background:#106ba3; }
  .bp3-dark .bp3-control.bp3-switch input:checked:not(:disabled):active ~ .bp3-control-indicator{
    background:#0e5a8a; }
  .bp3-dark .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator{
    background:rgba(14, 90, 138, 0.5); }
    .bp3-dark .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator::before{
      background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-switch .bp3-control-indicator::before{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background:#394b59; }
  .bp3-dark .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator::before{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-control.bp3-switch .bp3-switch-inner-text{
    text-align:center;
    font-size:0.7em; }
  .bp3-control.bp3-switch .bp3-control-indicator-child:first-child{
    visibility:hidden;
    margin-right:1.2em;
    margin-left:0.5em;
    line-height:0; }
  .bp3-control.bp3-switch .bp3-control-indicator-child:last-child{
    visibility:visible;
    margin-right:0.5em;
    margin-left:1.2em;
    line-height:1em; }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator .bp3-control-indicator-child:first-child{
    visibility:visible;
    line-height:1em; }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator .bp3-control-indicator-child:last-child{
    visibility:hidden;
    line-height:0; }
  .bp3-dark .bp3-control{
    color:#f5f8fa; }
    .bp3-dark .bp3-control.bp3-disabled{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-control .bp3-control-indicator{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#394b59;
      background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
      background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0)); }
    .bp3-dark .bp3-control:hover .bp3-control-indicator{
      background-color:#30404d; }
    .bp3-dark .bp3-control input:not(:disabled):active ~ .bp3-control-indicator{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background:#202b33; }
    .bp3-dark .bp3-control input:disabled ~ .bp3-control-indicator{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      cursor:not-allowed; }
    .bp3-dark .bp3-control.bp3-checkbox input:disabled:checked ~ .bp3-control-indicator, .bp3-dark .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
      color:rgba(167, 182, 194, 0.6); }
.bp3-file-input{
  display:inline-block;
  position:relative;
  cursor:pointer;
  height:30px; }
  .bp3-file-input input{
    opacity:0;
    margin:0;
    min-width:200px; }
    .bp3-file-input input:disabled + .bp3-file-upload-input,
    .bp3-file-input input.bp3-disabled + .bp3-file-upload-input{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(206, 217, 224, 0.5);
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6);
      resize:none; }
      .bp3-file-input input:disabled + .bp3-file-upload-input::after,
      .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after{
        outline:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        background-color:rgba(206, 217, 224, 0.5);
        background-image:none;
        cursor:not-allowed;
        color:rgba(92, 112, 128, 0.6); }
        .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active, .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active:hover,
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active,
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active:hover{
          background:rgba(206, 217, 224, 0.7); }
      .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input, .bp3-dark
      .bp3-file-input input.bp3-disabled + .bp3-file-upload-input{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:rgba(57, 75, 89, 0.5);
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input::after, .bp3-dark
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after{
          -webkit-box-shadow:none;
                  box-shadow:none;
          background-color:rgba(57, 75, 89, 0.5);
          background-image:none;
          color:rgba(167, 182, 194, 0.6); }
          .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active, .bp3-dark
          .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active{
            background:rgba(57, 75, 89, 0.7); }
  .bp3-file-input.bp3-file-input-has-selection .bp3-file-upload-input{
    color:#182026; }
  .bp3-dark .bp3-file-input.bp3-file-input-has-selection .bp3-file-upload-input{
    color:#f5f8fa; }
  .bp3-file-input.bp3-fill{
    width:100%; }
  .bp3-file-input.bp3-large,
  .bp3-large .bp3-file-input{
    height:40px; }
  .bp3-file-input .bp3-file-upload-input-custom-text::after{
    content:attr(bp3-button-text); }

.bp3-file-upload-input{
  outline:none;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  height:30px;
  padding:0 10px;
  vertical-align:middle;
  line-height:30px;
  color:#182026;
  font-size:14px;
  font-weight:400;
  -webkit-transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  -webkit-appearance:none;
     -moz-appearance:none;
          appearance:none;
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  position:absolute;
  top:0;
  right:0;
  left:0;
  padding-right:80px;
  color:rgba(92, 112, 128, 0.6);
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-file-upload-input::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input:focus, .bp3-file-upload-input.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-file-upload-input[type="search"], .bp3-file-upload-input.bp3-round{
    border-radius:30px;
    -webkit-box-sizing:border-box;
            box-sizing:border-box;
    padding-left:10px; }
  .bp3-file-upload-input[readonly]{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-file-upload-input:disabled, .bp3-file-upload-input.bp3-disabled{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(206, 217, 224, 0.5);
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6);
    resize:none; }
  .bp3-file-upload-input::after{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    color:#182026;
    min-width:24px;
    min-height:24px;
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    position:absolute;
    top:0;
    right:0;
    margin:3px;
    border-radius:3px;
    width:70px;
    text-align:center;
    line-height:24px;
    content:"Browse"; }
    .bp3-file-upload-input::after:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
      background-clip:padding-box;
      background-color:#ebf1f5; }
    .bp3-file-upload-input::after:active, .bp3-file-upload-input::after.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#d8e1e8;
      background-image:none; }
    .bp3-file-upload-input::after:disabled, .bp3-file-upload-input::after.bp3-disabled{
      outline:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(206, 217, 224, 0.5);
      background-image:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-file-upload-input::after:disabled.bp3-active, .bp3-file-upload-input::after:disabled.bp3-active:hover, .bp3-file-upload-input::after.bp3-disabled.bp3-active, .bp3-file-upload-input::after.bp3-disabled.bp3-active:hover{
        background:rgba(206, 217, 224, 0.7); }
  .bp3-file-upload-input:hover::after{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5; }
  .bp3-file-upload-input:active::after{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none; }
  .bp3-large .bp3-file-upload-input{
    height:40px;
    line-height:40px;
    font-size:16px;
    padding-right:95px; }
    .bp3-large .bp3-file-upload-input[type="search"], .bp3-large .bp3-file-upload-input.bp3-round{
      padding:0 15px; }
    .bp3-large .bp3-file-upload-input::after{
      min-width:30px;
      min-height:30px;
      margin:5px;
      width:85px;
      line-height:30px; }
  .bp3-dark .bp3-file-upload-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa;
    color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-file-upload-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-file-upload-input:disabled, .bp3-dark .bp3-file-upload-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::after{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#394b59;
      background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
      background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
      color:#f5f8fa; }
      .bp3-dark .bp3-file-upload-input::after:hover, .bp3-dark .bp3-file-upload-input::after:active, .bp3-dark .bp3-file-upload-input::after.bp3-active{
        color:#f5f8fa; }
      .bp3-dark .bp3-file-upload-input::after:hover{
        -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
        background-color:#30404d; }
      .bp3-dark .bp3-file-upload-input::after:active, .bp3-dark .bp3-file-upload-input::after.bp3-active{
        -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
                box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
        background-color:#202b33;
        background-image:none; }
      .bp3-dark .bp3-file-upload-input::after:disabled, .bp3-dark .bp3-file-upload-input::after.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none;
        background-color:rgba(57, 75, 89, 0.5);
        background-image:none;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-file-upload-input::after:disabled.bp3-active, .bp3-dark .bp3-file-upload-input::after.bp3-disabled.bp3-active{
          background:rgba(57, 75, 89, 0.7); }
      .bp3-dark .bp3-file-upload-input::after .bp3-button-spinner .bp3-spinner-head{
        background:rgba(16, 22, 26, 0.5);
        stroke:#8a9ba8; }
    .bp3-dark .bp3-file-upload-input:hover::after{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#30404d; }
    .bp3-dark .bp3-file-upload-input:active::after{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#202b33;
      background-image:none; }

.bp3-file-upload-input::after{
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
.bp3-form-group{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:0 0 15px; }
  .bp3-form-group label.bp3-label{
    margin-bottom:5px; }
  .bp3-form-group .bp3-control{
    margin-top:7px; }
  .bp3-form-group .bp3-form-helper-text{
    margin-top:5px;
    color:#5c7080;
    font-size:12px; }
  .bp3-form-group.bp3-intent-primary .bp3-form-helper-text{
    color:#106ba3; }
  .bp3-form-group.bp3-intent-success .bp3-form-helper-text{
    color:#0d8050; }
  .bp3-form-group.bp3-intent-warning .bp3-form-helper-text{
    color:#bf7326; }
  .bp3-form-group.bp3-intent-danger .bp3-form-helper-text{
    color:#c23030; }
  .bp3-form-group.bp3-inline{
    -webkit-box-orient:horizontal;
    -webkit-box-direction:normal;
        -ms-flex-direction:row;
            flex-direction:row;
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start; }
    .bp3-form-group.bp3-inline.bp3-large label.bp3-label{
      margin:0 10px 0 0;
      line-height:40px; }
    .bp3-form-group.bp3-inline label.bp3-label{
      margin:0 10px 0 0;
      line-height:30px; }
  .bp3-form-group.bp3-disabled .bp3-label,
  .bp3-form-group.bp3-disabled .bp3-text-muted,
  .bp3-form-group.bp3-disabled .bp3-form-helper-text{
    color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-dark .bp3-form-group.bp3-intent-primary .bp3-form-helper-text{
    color:#48aff0; }
  .bp3-dark .bp3-form-group.bp3-intent-success .bp3-form-helper-text{
    color:#3dcc91; }
  .bp3-dark .bp3-form-group.bp3-intent-warning .bp3-form-helper-text{
    color:#ffb366; }
  .bp3-dark .bp3-form-group.bp3-intent-danger .bp3-form-helper-text{
    color:#ff7373; }
  .bp3-dark .bp3-form-group .bp3-form-helper-text{
    color:#a7b6c2; }
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-label,
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-text-muted,
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-form-helper-text{
    color:rgba(167, 182, 194, 0.6) !important; }
.bp3-input-group{
  display:block;
  position:relative; }
  .bp3-input-group .bp3-input{
    position:relative;
    width:100%; }
    .bp3-input-group .bp3-input:not(:first-child){
      padding-left:30px; }
    .bp3-input-group .bp3-input:not(:last-child){
      padding-right:30px; }
  .bp3-input-group .bp3-input-action,
  .bp3-input-group > .bp3-button,
  .bp3-input-group > .bp3-icon{
    position:absolute;
    top:0; }
    .bp3-input-group .bp3-input-action:first-child,
    .bp3-input-group > .bp3-button:first-child,
    .bp3-input-group > .bp3-icon:first-child{
      left:0; }
    .bp3-input-group .bp3-input-action:last-child,
    .bp3-input-group > .bp3-button:last-child,
    .bp3-input-group > .bp3-icon:last-child{
      right:0; }
  .bp3-input-group .bp3-button{
    min-width:24px;
    min-height:24px;
    margin:3px;
    padding:0 7px; }
    .bp3-input-group .bp3-button:empty{
      padding:0; }
  .bp3-input-group > .bp3-icon{
    z-index:1;
    color:#5c7080; }
    .bp3-input-group > .bp3-icon:empty{
      line-height:1;
      font-family:"Icons16", sans-serif;
      font-size:16px;
      font-weight:400;
      font-style:normal;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased; }
  .bp3-input-group > .bp3-icon,
  .bp3-input-group .bp3-input-action > .bp3-spinner{
    margin:7px; }
  .bp3-input-group .bp3-tag{
    margin:5px; }
  .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus),
  .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus){
    color:#5c7080; }
    .bp3-dark .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus), .bp3-dark
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus){
      color:#a7b6c2; }
    .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-standard, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-large,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-standard,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-large{
      color:#5c7080; }
  .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled,
  .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled{
    color:rgba(92, 112, 128, 0.6) !important; }
    .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon-standard, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon-large,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon-standard,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon-large{
      color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-input-group.bp3-disabled{
    cursor:not-allowed; }
    .bp3-input-group.bp3-disabled .bp3-icon{
      color:rgba(92, 112, 128, 0.6); }
  .bp3-input-group.bp3-large .bp3-button{
    min-width:30px;
    min-height:30px;
    margin:5px; }
  .bp3-input-group.bp3-large > .bp3-icon,
  .bp3-input-group.bp3-large .bp3-input-action > .bp3-spinner{
    margin:12px; }
  .bp3-input-group.bp3-large .bp3-input{
    height:40px;
    line-height:40px;
    font-size:16px; }
    .bp3-input-group.bp3-large .bp3-input[type="search"], .bp3-input-group.bp3-large .bp3-input.bp3-round{
      padding:0 15px; }
    .bp3-input-group.bp3-large .bp3-input:not(:first-child){
      padding-left:40px; }
    .bp3-input-group.bp3-large .bp3-input:not(:last-child){
      padding-right:40px; }
  .bp3-input-group.bp3-small .bp3-button{
    min-width:20px;
    min-height:20px;
    margin:2px; }
  .bp3-input-group.bp3-small .bp3-tag{
    min-width:20px;
    min-height:20px;
    margin:2px; }
  .bp3-input-group.bp3-small > .bp3-icon,
  .bp3-input-group.bp3-small .bp3-input-action > .bp3-spinner{
    margin:4px; }
  .bp3-input-group.bp3-small .bp3-input{
    height:24px;
    padding-right:8px;
    padding-left:8px;
    line-height:24px;
    font-size:12px; }
    .bp3-input-group.bp3-small .bp3-input[type="search"], .bp3-input-group.bp3-small .bp3-input.bp3-round{
      padding:0 12px; }
    .bp3-input-group.bp3-small .bp3-input:not(:first-child){
      padding-left:24px; }
    .bp3-input-group.bp3-small .bp3-input:not(:last-child){
      padding-right:24px; }
  .bp3-input-group.bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:100%; }
  .bp3-input-group.bp3-round .bp3-button,
  .bp3-input-group.bp3-round .bp3-input,
  .bp3-input-group.bp3-round .bp3-tag{
    border-radius:30px; }
  .bp3-dark .bp3-input-group .bp3-icon{
    color:#a7b6c2; }
  .bp3-dark .bp3-input-group.bp3-disabled .bp3-icon{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-input-group.bp3-intent-primary .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-primary .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-primary .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #137cbd;
              box-shadow:inset 0 0 0 1px #137cbd; }
    .bp3-input-group.bp3-intent-primary .bp3-input:disabled, .bp3-input-group.bp3-intent-primary .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-primary > .bp3-icon{
    color:#106ba3; }
    .bp3-dark .bp3-input-group.bp3-intent-primary > .bp3-icon{
      color:#48aff0; }
  .bp3-input-group.bp3-intent-success .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-success .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-success .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #0f9960;
              box-shadow:inset 0 0 0 1px #0f9960; }
    .bp3-input-group.bp3-intent-success .bp3-input:disabled, .bp3-input-group.bp3-intent-success .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-success > .bp3-icon{
    color:#0d8050; }
    .bp3-dark .bp3-input-group.bp3-intent-success > .bp3-icon{
      color:#3dcc91; }
  .bp3-input-group.bp3-intent-warning .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-warning .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-warning .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #d9822b;
              box-shadow:inset 0 0 0 1px #d9822b; }
    .bp3-input-group.bp3-intent-warning .bp3-input:disabled, .bp3-input-group.bp3-intent-warning .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-warning > .bp3-icon{
    color:#bf7326; }
    .bp3-dark .bp3-input-group.bp3-intent-warning > .bp3-icon{
      color:#ffb366; }
  .bp3-input-group.bp3-intent-danger .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-danger .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-danger .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #db3737;
              box-shadow:inset 0 0 0 1px #db3737; }
    .bp3-input-group.bp3-intent-danger .bp3-input:disabled, .bp3-input-group.bp3-intent-danger .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-danger > .bp3-icon{
    color:#c23030; }
    .bp3-dark .bp3-input-group.bp3-intent-danger > .bp3-icon{
      color:#ff7373; }
.bp3-input{
  outline:none;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  height:30px;
  padding:0 10px;
  vertical-align:middle;
  line-height:30px;
  color:#182026;
  font-size:14px;
  font-weight:400;
  -webkit-transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  -webkit-appearance:none;
     -moz-appearance:none;
          appearance:none; }
  .bp3-input::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input:focus, .bp3-input.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-input[type="search"], .bp3-input.bp3-round{
    border-radius:30px;
    -webkit-box-sizing:border-box;
            box-sizing:border-box;
    padding-left:10px; }
  .bp3-input[readonly]{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-input:disabled, .bp3-input.bp3-disabled{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(206, 217, 224, 0.5);
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6);
    resize:none; }
  .bp3-input.bp3-large{
    height:40px;
    line-height:40px;
    font-size:16px; }
    .bp3-input.bp3-large[type="search"], .bp3-input.bp3-large.bp3-round{
      padding:0 15px; }
  .bp3-input.bp3-small{
    height:24px;
    padding-right:8px;
    padding-left:8px;
    line-height:24px;
    font-size:12px; }
    .bp3-input.bp3-small[type="search"], .bp3-input.bp3-small.bp3-round{
      padding:0 12px; }
  .bp3-input.bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:100%; }
  .bp3-dark .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa; }
    .bp3-dark .bp3-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-input:disabled, .bp3-dark .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      color:rgba(167, 182, 194, 0.6); }
  .bp3-input.bp3-intent-primary{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-primary:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-primary[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #137cbd;
              box-shadow:inset 0 0 0 1px #137cbd; }
    .bp3-input.bp3-intent-primary:disabled, .bp3-input.bp3-intent-primary.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-primary:focus{
        -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-primary[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #137cbd;
                box-shadow:inset 0 0 0 1px #137cbd; }
      .bp3-dark .bp3-input.bp3-intent-primary:disabled, .bp3-dark .bp3-input.bp3-intent-primary.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-success{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-success:focus{
      -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-success[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #0f9960;
              box-shadow:inset 0 0 0 1px #0f9960; }
    .bp3-input.bp3-intent-success:disabled, .bp3-input.bp3-intent-success.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-success{
      -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-success:focus{
        -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #0f9960, 0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-success[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #0f9960;
                box-shadow:inset 0 0 0 1px #0f9960; }
      .bp3-dark .bp3-input.bp3-intent-success:disabled, .bp3-dark .bp3-input.bp3-intent-success.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-warning{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-warning:focus{
      -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-warning[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #d9822b;
              box-shadow:inset 0 0 0 1px #d9822b; }
    .bp3-input.bp3-intent-warning:disabled, .bp3-input.bp3-intent-warning.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-warning:focus{
        -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #d9822b, 0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-warning[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #d9822b;
                box-shadow:inset 0 0 0 1px #d9822b; }
      .bp3-dark .bp3-input.bp3-intent-warning:disabled, .bp3-dark .bp3-input.bp3-intent-warning.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-danger{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-danger:focus{
      -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-danger[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #db3737;
              box-shadow:inset 0 0 0 1px #db3737; }
    .bp3-input.bp3-intent-danger:disabled, .bp3-input.bp3-intent-danger.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-danger:focus{
        -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #db3737, 0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-danger[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #db3737;
                box-shadow:inset 0 0 0 1px #db3737; }
      .bp3-dark .bp3-input.bp3-intent-danger:disabled, .bp3-dark .bp3-input.bp3-intent-danger.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input::-ms-clear{
    display:none; }
textarea.bp3-input{
  max-width:100%;
  padding:10px; }
  textarea.bp3-input, textarea.bp3-input.bp3-large, textarea.bp3-input.bp3-small{
    height:auto;
    line-height:inherit; }
  textarea.bp3-input.bp3-small{
    padding:8px; }
  .bp3-dark textarea.bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa; }
    .bp3-dark textarea.bp3-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark textarea.bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark textarea.bp3-input:disabled, .bp3-dark textarea.bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      color:rgba(167, 182, 194, 0.6); }
label.bp3-label{
  display:block;
  margin-top:0;
  margin-bottom:15px; }
  label.bp3-label .bp3-html-select,
  label.bp3-label .bp3-input,
  label.bp3-label .bp3-select,
  label.bp3-label .bp3-slider,
  label.bp3-label .bp3-popover-wrapper{
    display:block;
    margin-top:5px;
    text-transform:none; }
  label.bp3-label .bp3-button-group{
    margin-top:5px; }
  label.bp3-label .bp3-select select,
  label.bp3-label .bp3-html-select select{
    width:100%;
    vertical-align:top;
    font-weight:400; }
  label.bp3-label.bp3-disabled,
  label.bp3-label.bp3-disabled .bp3-text-muted{
    color:rgba(92, 112, 128, 0.6); }
  label.bp3-label.bp3-inline{
    line-height:30px; }
    label.bp3-label.bp3-inline .bp3-html-select,
    label.bp3-label.bp3-inline .bp3-input,
    label.bp3-label.bp3-inline .bp3-input-group,
    label.bp3-label.bp3-inline .bp3-select,
    label.bp3-label.bp3-inline .bp3-popover-wrapper{
      display:inline-block;
      margin:0 0 0 5px;
      vertical-align:top; }
    label.bp3-label.bp3-inline .bp3-button-group{
      margin:0 0 0 5px; }
    label.bp3-label.bp3-inline .bp3-input-group .bp3-input{
      margin-left:0; }
    label.bp3-label.bp3-inline.bp3-large{
      line-height:40px; }
  label.bp3-label:not(.bp3-inline) .bp3-popover-target{
    display:block; }
  .bp3-dark label.bp3-label{
    color:#f5f8fa; }
    .bp3-dark label.bp3-label.bp3-disabled,
    .bp3-dark label.bp3-label.bp3-disabled .bp3-text-muted{
      color:rgba(167, 182, 194, 0.6); }
.bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button{
  -webkit-box-flex:1;
      -ms-flex:1 1 14px;
          flex:1 1 14px;
  width:30px;
  min-height:0;
  padding:0; }
  .bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button:first-child{
    border-radius:0 3px 0 0; }
  .bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button:last-child{
    border-radius:0 0 3px 0; }

.bp3-numeric-input .bp3-button-group.bp3-vertical:first-child > .bp3-button:first-child{
  border-radius:3px 0 0 0; }

.bp3-numeric-input .bp3-button-group.bp3-vertical:first-child > .bp3-button:last-child{
  border-radius:0 0 0 3px; }

.bp3-numeric-input.bp3-large .bp3-button-group.bp3-vertical > .bp3-button{
  width:40px; }

form{
  display:block; }
.bp3-html-select select,
.bp3-select select{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  border:none;
  border-radius:3px;
  cursor:pointer;
  padding:5px 10px;
  vertical-align:middle;
  text-align:left;
  font-size:14px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
  background-color:#f5f8fa;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
  color:#182026;
  border-radius:3px;
  width:100%;
  height:30px;
  padding:0 25px 0 10px;
  -moz-appearance:none;
  -webkit-appearance:none; }
  .bp3-html-select select > *, .bp3-select select > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-html-select select > .bp3-fill, .bp3-select select > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-html-select select::before,
  .bp3-select select::before, .bp3-html-select select > *, .bp3-select select > *{
    margin-right:7px; }
  .bp3-html-select select:empty::before,
  .bp3-select select:empty::before,
  .bp3-html-select select > :last-child,
  .bp3-select select > :last-child{
    margin-right:0; }
  .bp3-html-select select:hover,
  .bp3-select select:hover{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5; }
  .bp3-html-select select:active,
  .bp3-select select:active, .bp3-html-select select.bp3-active,
  .bp3-select select.bp3-active{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none; }
  .bp3-html-select select:disabled,
  .bp3-select select:disabled, .bp3-html-select select.bp3-disabled,
  .bp3-select select.bp3-disabled{
    outline:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    background-color:rgba(206, 217, 224, 0.5);
    background-image:none;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
    .bp3-html-select select:disabled.bp3-active,
    .bp3-select select:disabled.bp3-active, .bp3-html-select select:disabled.bp3-active:hover,
    .bp3-select select:disabled.bp3-active:hover, .bp3-html-select select.bp3-disabled.bp3-active,
    .bp3-select select.bp3-disabled.bp3-active, .bp3-html-select select.bp3-disabled.bp3-active:hover,
    .bp3-select select.bp3-disabled.bp3-active:hover{
      background:rgba(206, 217, 224, 0.7); }

.bp3-html-select.bp3-minimal select,
.bp3-select.bp3-minimal select{
  -webkit-box-shadow:none;
          box-shadow:none;
  background:none; }
  .bp3-html-select.bp3-minimal select:hover,
  .bp3-select.bp3-minimal select:hover{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(167, 182, 194, 0.3);
    text-decoration:none;
    color:#182026; }
  .bp3-html-select.bp3-minimal select:active,
  .bp3-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal select.bp3-active,
  .bp3-select.bp3-minimal select.bp3-active{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(115, 134, 148, 0.3);
    color:#182026; }
  .bp3-html-select.bp3-minimal select:disabled,
  .bp3-select.bp3-minimal select:disabled, .bp3-html-select.bp3-minimal select:disabled:hover,
  .bp3-select.bp3-minimal select:disabled:hover, .bp3-html-select.bp3-minimal select.bp3-disabled,
  .bp3-select.bp3-minimal select.bp3-disabled, .bp3-html-select.bp3-minimal select.bp3-disabled:hover,
  .bp3-select.bp3-minimal select.bp3-disabled:hover{
    background:none;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
    .bp3-html-select.bp3-minimal select:disabled.bp3-active,
    .bp3-select.bp3-minimal select:disabled.bp3-active, .bp3-html-select.bp3-minimal select:disabled:hover.bp3-active,
    .bp3-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-html-select.bp3-minimal select.bp3-disabled.bp3-active,
    .bp3-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-disabled:hover.bp3-active,
    .bp3-select.bp3-minimal select.bp3-disabled:hover.bp3-active{
      background:rgba(115, 134, 148, 0.3); }
  .bp3-dark .bp3-html-select.bp3-minimal select, .bp3-html-select.bp3-minimal .bp3-dark select,
  .bp3-dark .bp3-select.bp3-minimal select, .bp3-select.bp3-minimal .bp3-dark select{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none;
    color:inherit; }
    .bp3-dark .bp3-html-select.bp3-minimal select:hover, .bp3-html-select.bp3-minimal .bp3-dark select:hover,
    .bp3-dark .bp3-select.bp3-minimal select:hover, .bp3-select.bp3-minimal .bp3-dark select:hover, .bp3-dark .bp3-html-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal .bp3-dark select:active,
    .bp3-dark .bp3-select.bp3-minimal select:active, .bp3-select.bp3-minimal .bp3-dark select:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-active,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none; }
    .bp3-dark .bp3-html-select.bp3-minimal select:hover, .bp3-html-select.bp3-minimal .bp3-dark select:hover,
    .bp3-dark .bp3-select.bp3-minimal select:hover, .bp3-select.bp3-minimal .bp3-dark select:hover{
      background:rgba(138, 155, 168, 0.15); }
    .bp3-dark .bp3-html-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal .bp3-dark select:active,
    .bp3-dark .bp3-select.bp3-minimal select:active, .bp3-select.bp3-minimal .bp3-dark select:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-active,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-active{
      background:rgba(138, 155, 168, 0.3);
      color:#f5f8fa; }
    .bp3-dark .bp3-html-select.bp3-minimal select:disabled, .bp3-html-select.bp3-minimal .bp3-dark select:disabled,
    .bp3-dark .bp3-select.bp3-minimal select:disabled, .bp3-select.bp3-minimal .bp3-dark select:disabled, .bp3-dark .bp3-html-select.bp3-minimal select:disabled:hover, .bp3-html-select.bp3-minimal .bp3-dark select:disabled:hover,
    .bp3-dark .bp3-select.bp3-minimal select:disabled:hover, .bp3-select.bp3-minimal .bp3-dark select:disabled:hover, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled:hover,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled:hover{
      background:none;
      cursor:not-allowed;
      color:rgba(167, 182, 194, 0.6); }
      .bp3-dark .bp3-html-select.bp3-minimal select:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select:disabled.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select:disabled:hover.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-select.bp3-minimal .bp3-dark select:disabled:hover.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled:hover.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled:hover.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled:hover.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled:hover.bp3-active{
        background:rgba(138, 155, 168, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-primary,
  .bp3-select.bp3-minimal select.bp3-intent-primary{
    color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover,
    .bp3-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-html-select.bp3-minimal select.bp3-intent-primary:active,
    .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover,
    .bp3-select.bp3-minimal select.bp3-intent-primary:hover{
      background:rgba(19, 124, 189, 0.15);
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:active,
    .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active{
      background:rgba(19, 124, 189, 0.3);
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled{
      background:none;
      color:rgba(16, 107, 163, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active{
        background:rgba(19, 124, 189, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
      stroke:#106ba3; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary{
      color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.2);
        color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(72, 175, 240, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-success,
  .bp3-select.bp3-minimal select.bp3-intent-success{
    color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:hover,
    .bp3-select.bp3-minimal select.bp3-intent-success:hover, .bp3-html-select.bp3-minimal select.bp3-intent-success:active,
    .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:hover,
    .bp3-select.bp3-minimal select.bp3-intent-success:hover{
      background:rgba(15, 153, 96, 0.15);
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:active,
    .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active{
      background:rgba(15, 153, 96, 0.3);
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled{
      background:none;
      color:rgba(13, 128, 80, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active{
        background:rgba(15, 153, 96, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-success .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
      stroke:#0d8050; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success{
      color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.2);
        color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(61, 204, 145, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-warning,
  .bp3-select.bp3-minimal select.bp3-intent-warning{
    color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover,
    .bp3-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-html-select.bp3-minimal select.bp3-intent-warning:active,
    .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover,
    .bp3-select.bp3-minimal select.bp3-intent-warning:hover{
      background:rgba(217, 130, 43, 0.15);
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:active,
    .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active{
      background:rgba(217, 130, 43, 0.3);
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled{
      background:none;
      color:rgba(191, 115, 38, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active{
        background:rgba(217, 130, 43, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
      stroke:#bf7326; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning{
      color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.2);
        color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(255, 179, 102, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-danger,
  .bp3-select.bp3-minimal select.bp3-intent-danger{
    color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover,
    .bp3-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-html-select.bp3-minimal select.bp3-intent-danger:active,
    .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover,
    .bp3-select.bp3-minimal select.bp3-intent-danger:hover{
      background:rgba(219, 55, 55, 0.15);
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:active,
    .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active{
      background:rgba(219, 55, 55, 0.3);
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled{
      background:none;
      color:rgba(194, 48, 48, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active{
        background:rgba(219, 55, 55, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
      stroke:#c23030; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger{
      color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.2);
        color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(255, 115, 115, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }

.bp3-html-select.bp3-large select,
.bp3-select.bp3-large select{
  height:40px;
  padding-right:35px;
  font-size:16px; }

.bp3-dark .bp3-html-select select, .bp3-dark .bp3-select select{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
  background-color:#394b59;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
  color:#f5f8fa; }
  .bp3-dark .bp3-html-select select:hover, .bp3-dark .bp3-select select:hover, .bp3-dark .bp3-html-select select:active, .bp3-dark .bp3-select select:active, .bp3-dark .bp3-html-select select.bp3-active, .bp3-dark .bp3-select select.bp3-active{
    color:#f5f8fa; }
  .bp3-dark .bp3-html-select select:hover, .bp3-dark .bp3-select select:hover{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#30404d; }
  .bp3-dark .bp3-html-select select:active, .bp3-dark .bp3-select select:active, .bp3-dark .bp3-html-select select.bp3-active, .bp3-dark .bp3-select select.bp3-active{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#202b33;
    background-image:none; }
  .bp3-dark .bp3-html-select select:disabled, .bp3-dark .bp3-select select:disabled, .bp3-dark .bp3-html-select select.bp3-disabled, .bp3-dark .bp3-select select.bp3-disabled{
    -webkit-box-shadow:none;
            box-shadow:none;
    background-color:rgba(57, 75, 89, 0.5);
    background-image:none;
    color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-html-select select:disabled.bp3-active, .bp3-dark .bp3-select select:disabled.bp3-active, .bp3-dark .bp3-html-select select.bp3-disabled.bp3-active, .bp3-dark .bp3-select select.bp3-disabled.bp3-active{
      background:rgba(57, 75, 89, 0.7); }
  .bp3-dark .bp3-html-select select .bp3-button-spinner .bp3-spinner-head, .bp3-dark .bp3-select select .bp3-button-spinner .bp3-spinner-head{
    background:rgba(16, 22, 26, 0.5);
    stroke:#8a9ba8; }

.bp3-html-select select:disabled,
.bp3-select select:disabled{
  -webkit-box-shadow:none;
          box-shadow:none;
  background-color:rgba(206, 217, 224, 0.5);
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-html-select .bp3-icon,
.bp3-select .bp3-icon, .bp3-select::after{
  position:absolute;
  top:7px;
  right:7px;
  color:#5c7080;
  pointer-events:none; }
  .bp3-html-select .bp3-disabled.bp3-icon,
  .bp3-select .bp3-disabled.bp3-icon, .bp3-disabled.bp3-select::after{
    color:rgba(92, 112, 128, 0.6); }
.bp3-html-select,
.bp3-select{
  display:inline-block;
  position:relative;
  vertical-align:middle;
  letter-spacing:normal; }
  .bp3-html-select select::-ms-expand,
  .bp3-select select::-ms-expand{
    display:none; }
  .bp3-html-select .bp3-icon,
  .bp3-select .bp3-icon{
    color:#5c7080; }
    .bp3-html-select .bp3-icon:hover,
    .bp3-select .bp3-icon:hover{
      color:#182026; }
    .bp3-dark .bp3-html-select .bp3-icon, .bp3-dark
    .bp3-select .bp3-icon{
      color:#a7b6c2; }
      .bp3-dark .bp3-html-select .bp3-icon:hover, .bp3-dark
      .bp3-select .bp3-icon:hover{
        color:#f5f8fa; }
  .bp3-html-select.bp3-large::after,
  .bp3-html-select.bp3-large .bp3-icon,
  .bp3-select.bp3-large::after,
  .bp3-select.bp3-large .bp3-icon{
    top:12px;
    right:12px; }
  .bp3-html-select.bp3-fill,
  .bp3-html-select.bp3-fill select,
  .bp3-select.bp3-fill,
  .bp3-select.bp3-fill select{
    width:100%; }
  .bp3-dark .bp3-html-select option, .bp3-dark
  .bp3-select option{
    background-color:#30404d;
    color:#f5f8fa; }
  .bp3-dark .bp3-html-select::after, .bp3-dark
  .bp3-select::after{
    color:#a7b6c2; }

.bp3-select::after{
  line-height:1;
  font-family:"Icons16", sans-serif;
  font-size:16px;
  font-weight:400;
  font-style:normal;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  content:""; }
.bp3-running-text table, table.bp3-html-table{
  border-spacing:0;
  font-size:14px; }
  .bp3-running-text table th, table.bp3-html-table th,
  .bp3-running-text table td,
  table.bp3-html-table td{
    padding:11px;
    vertical-align:top;
    text-align:left; }
  .bp3-running-text table th, table.bp3-html-table th{
    color:#182026;
    font-weight:600; }
  
  .bp3-running-text table td,
  table.bp3-html-table td{
    color:#182026; }
  .bp3-running-text table tbody tr:first-child th, table.bp3-html-table tbody tr:first-child th,
  .bp3-running-text table tbody tr:first-child td,
  table.bp3-html-table tbody tr:first-child td{
    -webkit-box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-running-text table th, .bp3-running-text .bp3-dark table th, .bp3-dark table.bp3-html-table th{
    color:#f5f8fa; }
  .bp3-dark .bp3-running-text table td, .bp3-running-text .bp3-dark table td, .bp3-dark table.bp3-html-table td{
    color:#f5f8fa; }
  .bp3-dark .bp3-running-text table tbody tr:first-child th, .bp3-running-text .bp3-dark table tbody tr:first-child th, .bp3-dark table.bp3-html-table tbody tr:first-child th,
  .bp3-dark .bp3-running-text table tbody tr:first-child td,
  .bp3-running-text .bp3-dark table tbody tr:first-child td,
  .bp3-dark table.bp3-html-table tbody tr:first-child td{
    -webkit-box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15); }

table.bp3-html-table.bp3-html-table-condensed th,
table.bp3-html-table.bp3-html-table-condensed td, table.bp3-html-table.bp3-small th,
table.bp3-html-table.bp3-small td{
  padding-top:6px;
  padding-bottom:6px; }

table.bp3-html-table.bp3-html-table-striped tbody tr:nth-child(odd) td{
  background:rgba(191, 204, 214, 0.15); }

table.bp3-html-table.bp3-html-table-bordered th:not(:first-child){
  -webkit-box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-html-table-bordered tbody tr td{
  -webkit-box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15); }
  table.bp3-html-table.bp3-html-table-bordered tbody tr td:not(:first-child){
    -webkit-box-shadow:inset 1px 1px 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 1px 1px 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td{
  -webkit-box-shadow:none;
          box-shadow:none; }
  table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td:not(:first-child){
    -webkit-box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-interactive tbody tr:hover td{
  background-color:rgba(191, 204, 214, 0.3);
  cursor:pointer; }

table.bp3-html-table.bp3-interactive tbody tr:active td{
  background-color:rgba(191, 204, 214, 0.4); }

.bp3-dark table.bp3-html-table.bp3-html-table-striped tbody tr:nth-child(odd) td{
  background:rgba(92, 112, 128, 0.15); }

.bp3-dark table.bp3-html-table.bp3-html-table-bordered th:not(:first-child){
  -webkit-box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15);
          box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15); }

.bp3-dark table.bp3-html-table.bp3-html-table-bordered tbody tr td{
  -webkit-box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15);
          box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15); }
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered tbody tr td:not(:first-child){
    -webkit-box-shadow:inset 1px 1px 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 1px 1px 0 0 rgba(255, 255, 255, 0.15); }

.bp3-dark table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td{
  -webkit-box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15);
          box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15); }
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td:first-child{
    -webkit-box-shadow:none;
            box-shadow:none; }

.bp3-dark table.bp3-html-table.bp3-interactive tbody tr:hover td{
  background-color:rgba(92, 112, 128, 0.3);
  cursor:pointer; }

.bp3-dark table.bp3-html-table.bp3-interactive tbody tr:active td{
  background-color:rgba(92, 112, 128, 0.4); }

.bp3-key-combo{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center; }
  .bp3-key-combo > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-key-combo > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-key-combo::before,
  .bp3-key-combo > *{
    margin-right:5px; }
  .bp3-key-combo:empty::before,
  .bp3-key-combo > :last-child{
    margin-right:0; }

.bp3-hotkey-dialog{
  top:40px;
  padding-bottom:0; }
  .bp3-hotkey-dialog .bp3-dialog-body{
    margin:0;
    padding:0; }
  .bp3-hotkey-dialog .bp3-hotkey-label{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1; }

.bp3-hotkey-column{
  margin:auto;
  max-height:80vh;
  overflow-y:auto;
  padding:30px; }
  .bp3-hotkey-column .bp3-heading{
    margin-bottom:20px; }
    .bp3-hotkey-column .bp3-heading:not(:first-child){
      margin-top:40px; }

.bp3-hotkey{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:justify;
      -ms-flex-pack:justify;
          justify-content:space-between;
  margin-right:0;
  margin-left:0; }
  .bp3-hotkey:not(:last-child){
    margin-bottom:10px; }
.bp3-icon{
  display:inline-block;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  vertical-align:text-bottom; }
  .bp3-icon:not(:empty)::before{
    content:"" !important;
    content:unset !important; }
  .bp3-icon > svg{
    display:block; }
    .bp3-icon > svg:not([fill]){
      fill:currentColor; }

.bp3-icon.bp3-intent-primary, .bp3-icon-standard.bp3-intent-primary, .bp3-icon-large.bp3-intent-primary{
  color:#106ba3; }
  .bp3-dark .bp3-icon.bp3-intent-primary, .bp3-dark .bp3-icon-standard.bp3-intent-primary, .bp3-dark .bp3-icon-large.bp3-intent-primary{
    color:#48aff0; }

.bp3-icon.bp3-intent-success, .bp3-icon-standard.bp3-intent-success, .bp3-icon-large.bp3-intent-success{
  color:#0d8050; }
  .bp3-dark .bp3-icon.bp3-intent-success, .bp3-dark .bp3-icon-standard.bp3-intent-success, .bp3-dark .bp3-icon-large.bp3-intent-success{
    color:#3dcc91; }

.bp3-icon.bp3-intent-warning, .bp3-icon-standard.bp3-intent-warning, .bp3-icon-large.bp3-intent-warning{
  color:#bf7326; }
  .bp3-dark .bp3-icon.bp3-intent-warning, .bp3-dark .bp3-icon-standard.bp3-intent-warning, .bp3-dark .bp3-icon-large.bp3-intent-warning{
    color:#ffb366; }

.bp3-icon.bp3-intent-danger, .bp3-icon-standard.bp3-intent-danger, .bp3-icon-large.bp3-intent-danger{
  color:#c23030; }
  .bp3-dark .bp3-icon.bp3-intent-danger, .bp3-dark .bp3-icon-standard.bp3-intent-danger, .bp3-dark .bp3-icon-large.bp3-intent-danger{
    color:#ff7373; }

span.bp3-icon-standard{
  line-height:1;
  font-family:"Icons16", sans-serif;
  font-size:16px;
  font-weight:400;
  font-style:normal;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  display:inline-block; }

span.bp3-icon-large{
  line-height:1;
  font-family:"Icons20", sans-serif;
  font-size:20px;
  font-weight:400;
  font-style:normal;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  display:inline-block; }

span.bp3-icon:empty{
  line-height:1;
  font-family:"Icons20";
  font-size:inherit;
  font-weight:400;
  font-style:normal; }
  span.bp3-icon:empty::before{
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased; }

.bp3-icon-add::before{
  content:""; }

.bp3-icon-add-column-left::before{
  content:""; }

.bp3-icon-add-column-right::before{
  content:""; }

.bp3-icon-add-row-bottom::before{
  content:""; }

.bp3-icon-add-row-top::before{
  content:""; }

.bp3-icon-add-to-artifact::before{
  content:""; }

.bp3-icon-add-to-folder::before{
  content:""; }

.bp3-icon-airplane::before{
  content:""; }

.bp3-icon-align-center::before{
  content:""; }

.bp3-icon-align-justify::before{
  content:""; }

.bp3-icon-align-left::before{
  content:""; }

.bp3-icon-align-right::before{
  content:""; }

.bp3-icon-alignment-bottom::before{
  content:""; }

.bp3-icon-alignment-horizontal-center::before{
  content:""; }

.bp3-icon-alignment-left::before{
  content:""; }

.bp3-icon-alignment-right::before{
  content:""; }

.bp3-icon-alignment-top::before{
  content:""; }

.bp3-icon-alignment-vertical-center::before{
  content:""; }

.bp3-icon-annotation::before{
  content:""; }

.bp3-icon-application::before{
  content:""; }

.bp3-icon-applications::before{
  content:""; }

.bp3-icon-archive::before{
  content:""; }

.bp3-icon-arrow-bottom-left::before{
  content:"↙"; }

.bp3-icon-arrow-bottom-right::before{
  content:"↘"; }

.bp3-icon-arrow-down::before{
  content:"↓"; }

.bp3-icon-arrow-left::before{
  content:"←"; }

.bp3-icon-arrow-right::before{
  content:"→"; }

.bp3-icon-arrow-top-left::before{
  content:"↖"; }

.bp3-icon-arrow-top-right::before{
  content:"↗"; }

.bp3-icon-arrow-up::before{
  content:"↑"; }

.bp3-icon-arrows-horizontal::before{
  content:"↔"; }

.bp3-icon-arrows-vertical::before{
  content:"↕"; }

.bp3-icon-asterisk::before{
  content:"*"; }

.bp3-icon-automatic-updates::before{
  content:""; }

.bp3-icon-badge::before{
  content:""; }

.bp3-icon-ban-circle::before{
  content:""; }

.bp3-icon-bank-account::before{
  content:""; }

.bp3-icon-barcode::before{
  content:""; }

.bp3-icon-blank::before{
  content:""; }

.bp3-icon-blocked-person::before{
  content:""; }

.bp3-icon-bold::before{
  content:""; }

.bp3-icon-book::before{
  content:""; }

.bp3-icon-bookmark::before{
  content:""; }

.bp3-icon-box::before{
  content:""; }

.bp3-icon-briefcase::before{
  content:""; }

.bp3-icon-bring-data::before{
  content:""; }

.bp3-icon-build::before{
  content:""; }

.bp3-icon-calculator::before{
  content:""; }

.bp3-icon-calendar::before{
  content:""; }

.bp3-icon-camera::before{
  content:""; }

.bp3-icon-caret-down::before{
  content:"⌄"; }

.bp3-icon-caret-left::before{
  content:"〈"; }

.bp3-icon-caret-right::before{
  content:"〉"; }

.bp3-icon-caret-up::before{
  content:"⌃"; }

.bp3-icon-cell-tower::before{
  content:""; }

.bp3-icon-changes::before{
  content:""; }

.bp3-icon-chart::before{
  content:""; }

.bp3-icon-chat::before{
  content:""; }

.bp3-icon-chevron-backward::before{
  content:""; }

.bp3-icon-chevron-down::before{
  content:""; }

.bp3-icon-chevron-forward::before{
  content:""; }

.bp3-icon-chevron-left::before{
  content:""; }

.bp3-icon-chevron-right::before{
  content:""; }

.bp3-icon-chevron-up::before{
  content:""; }

.bp3-icon-circle::before{
  content:""; }

.bp3-icon-circle-arrow-down::before{
  content:""; }

.bp3-icon-circle-arrow-left::before{
  content:""; }

.bp3-icon-circle-arrow-right::before{
  content:""; }

.bp3-icon-circle-arrow-up::before{
  content:""; }

.bp3-icon-citation::before{
  content:""; }

.bp3-icon-clean::before{
  content:""; }

.bp3-icon-clipboard::before{
  content:""; }

.bp3-icon-cloud::before{
  content:"☁"; }

.bp3-icon-cloud-download::before{
  content:""; }

.bp3-icon-cloud-upload::before{
  content:""; }

.bp3-icon-code::before{
  content:""; }

.bp3-icon-code-block::before{
  content:""; }

.bp3-icon-cog::before{
  content:""; }

.bp3-icon-collapse-all::before{
  content:""; }

.bp3-icon-column-layout::before{
  content:""; }

.bp3-icon-comment::before{
  content:""; }

.bp3-icon-comparison::before{
  content:""; }

.bp3-icon-compass::before{
  content:""; }

.bp3-icon-compressed::before{
  content:""; }

.bp3-icon-confirm::before{
  content:""; }

.bp3-icon-console::before{
  content:""; }

.bp3-icon-contrast::before{
  content:""; }

.bp3-icon-control::before{
  content:""; }

.bp3-icon-credit-card::before{
  content:""; }

.bp3-icon-cross::before{
  content:"✗"; }

.bp3-icon-crown::before{
  content:""; }

.bp3-icon-cube::before{
  content:""; }

.bp3-icon-cube-add::before{
  content:""; }

.bp3-icon-cube-remove::before{
  content:""; }

.bp3-icon-curved-range-chart::before{
  content:""; }

.bp3-icon-cut::before{
  content:""; }

.bp3-icon-dashboard::before{
  content:""; }

.bp3-icon-data-lineage::before{
  content:""; }

.bp3-icon-database::before{
  content:""; }

.bp3-icon-delete::before{
  content:""; }

.bp3-icon-delta::before{
  content:"Δ"; }

.bp3-icon-derive-column::before{
  content:""; }

.bp3-icon-desktop::before{
  content:""; }

.bp3-icon-diagram-tree::before{
  content:""; }

.bp3-icon-direction-left::before{
  content:""; }

.bp3-icon-direction-right::before{
  content:""; }

.bp3-icon-disable::before{
  content:""; }

.bp3-icon-document::before{
  content:""; }

.bp3-icon-document-open::before{
  content:""; }

.bp3-icon-document-share::before{
  content:""; }

.bp3-icon-dollar::before{
  content:"$"; }

.bp3-icon-dot::before{
  content:"•"; }

.bp3-icon-double-caret-horizontal::before{
  content:""; }

.bp3-icon-double-caret-vertical::before{
  content:""; }

.bp3-icon-double-chevron-down::before{
  content:""; }

.bp3-icon-double-chevron-left::before{
  content:""; }

.bp3-icon-double-chevron-right::before{
  content:""; }

.bp3-icon-double-chevron-up::before{
  content:""; }

.bp3-icon-doughnut-chart::before{
  content:""; }

.bp3-icon-download::before{
  content:""; }

.bp3-icon-drag-handle-horizontal::before{
  content:""; }

.bp3-icon-drag-handle-vertical::before{
  content:""; }

.bp3-icon-draw::before{
  content:""; }

.bp3-icon-drive-time::before{
  content:""; }

.bp3-icon-duplicate::before{
  content:""; }

.bp3-icon-edit::before{
  content:"✎"; }

.bp3-icon-eject::before{
  content:"⏏"; }

.bp3-icon-endorsed::before{
  content:""; }

.bp3-icon-envelope::before{
  content:"✉"; }

.bp3-icon-equals::before{
  content:""; }

.bp3-icon-eraser::before{
  content:""; }

.bp3-icon-error::before{
  content:""; }

.bp3-icon-euro::before{
  content:"€"; }

.bp3-icon-exchange::before{
  content:""; }

.bp3-icon-exclude-row::before{
  content:""; }

.bp3-icon-expand-all::before{
  content:""; }

.bp3-icon-export::before{
  content:""; }

.bp3-icon-eye-off::before{
  content:""; }

.bp3-icon-eye-on::before{
  content:""; }

.bp3-icon-eye-open::before{
  content:""; }

.bp3-icon-fast-backward::before{
  content:""; }

.bp3-icon-fast-forward::before{
  content:""; }

.bp3-icon-feed::before{
  content:""; }

.bp3-icon-feed-subscribed::before{
  content:""; }

.bp3-icon-film::before{
  content:""; }

.bp3-icon-filter::before{
  content:""; }

.bp3-icon-filter-keep::before{
  content:""; }

.bp3-icon-filter-list::before{
  content:""; }

.bp3-icon-filter-open::before{
  content:""; }

.bp3-icon-filter-remove::before{
  content:""; }

.bp3-icon-flag::before{
  content:"⚑"; }

.bp3-icon-flame::before{
  content:""; }

.bp3-icon-flash::before{
  content:""; }

.bp3-icon-floppy-disk::before{
  content:""; }

.bp3-icon-flow-branch::before{
  content:""; }

.bp3-icon-flow-end::before{
  content:""; }

.bp3-icon-flow-linear::before{
  content:""; }

.bp3-icon-flow-review::before{
  content:""; }

.bp3-icon-flow-review-branch::before{
  content:""; }

.bp3-icon-flows::before{
  content:""; }

.bp3-icon-folder-close::before{
  content:""; }

.bp3-icon-folder-new::before{
  content:""; }

.bp3-icon-folder-open::before{
  content:""; }

.bp3-icon-folder-shared::before{
  content:""; }

.bp3-icon-folder-shared-open::before{
  content:""; }

.bp3-icon-follower::before{
  content:""; }

.bp3-icon-following::before{
  content:""; }

.bp3-icon-font::before{
  content:""; }

.bp3-icon-fork::before{
  content:""; }

.bp3-icon-form::before{
  content:""; }

.bp3-icon-full-circle::before{
  content:""; }

.bp3-icon-full-stacked-chart::before{
  content:""; }

.bp3-icon-fullscreen::before{
  content:""; }

.bp3-icon-function::before{
  content:""; }

.bp3-icon-gantt-chart::before{
  content:""; }

.bp3-icon-geolocation::before{
  content:""; }

.bp3-icon-geosearch::before{
  content:""; }

.bp3-icon-git-branch::before{
  content:""; }

.bp3-icon-git-commit::before{
  content:""; }

.bp3-icon-git-merge::before{
  content:""; }

.bp3-icon-git-new-branch::before{
  content:""; }

.bp3-icon-git-pull::before{
  content:""; }

.bp3-icon-git-push::before{
  content:""; }

.bp3-icon-git-repo::before{
  content:""; }

.bp3-icon-glass::before{
  content:""; }

.bp3-icon-globe::before{
  content:""; }

.bp3-icon-globe-network::before{
  content:""; }

.bp3-icon-graph::before{
  content:""; }

.bp3-icon-graph-remove::before{
  content:""; }

.bp3-icon-greater-than::before{
  content:""; }

.bp3-icon-greater-than-or-equal-to::before{
  content:""; }

.bp3-icon-grid::before{
  content:""; }

.bp3-icon-grid-view::before{
  content:""; }

.bp3-icon-group-objects::before{
  content:""; }

.bp3-icon-grouped-bar-chart::before{
  content:""; }

.bp3-icon-hand::before{
  content:""; }

.bp3-icon-hand-down::before{
  content:""; }

.bp3-icon-hand-left::before{
  content:""; }

.bp3-icon-hand-right::before{
  content:""; }

.bp3-icon-hand-up::before{
  content:""; }

.bp3-icon-header::before{
  content:""; }

.bp3-icon-header-one::before{
  content:""; }

.bp3-icon-header-two::before{
  content:""; }

.bp3-icon-headset::before{
  content:""; }

.bp3-icon-heart::before{
  content:"♥"; }

.bp3-icon-heart-broken::before{
  content:""; }

.bp3-icon-heat-grid::before{
  content:""; }

.bp3-icon-heatmap::before{
  content:""; }

.bp3-icon-help::before{
  content:"?"; }

.bp3-icon-helper-management::before{
  content:""; }

.bp3-icon-highlight::before{
  content:""; }

.bp3-icon-history::before{
  content:""; }

.bp3-icon-home::before{
  content:"⌂"; }

.bp3-icon-horizontal-bar-chart::before{
  content:""; }

.bp3-icon-horizontal-bar-chart-asc::before{
  content:""; }

.bp3-icon-horizontal-bar-chart-desc::before{
  content:""; }

.bp3-icon-horizontal-distribution::before{
  content:""; }

.bp3-icon-id-number::before{
  content:""; }

.bp3-icon-image-rotate-left::before{
  content:""; }

.bp3-icon-image-rotate-right::before{
  content:""; }

.bp3-icon-import::before{
  content:""; }

.bp3-icon-inbox::before{
  content:""; }

.bp3-icon-inbox-filtered::before{
  content:""; }

.bp3-icon-inbox-geo::before{
  content:""; }

.bp3-icon-inbox-search::before{
  content:""; }

.bp3-icon-inbox-update::before{
  content:""; }

.bp3-icon-info-sign::before{
  content:"ℹ"; }

.bp3-icon-inheritance::before{
  content:""; }

.bp3-icon-inner-join::before{
  content:""; }

.bp3-icon-insert::before{
  content:""; }

.bp3-icon-intersection::before{
  content:""; }

.bp3-icon-ip-address::before{
  content:""; }

.bp3-icon-issue::before{
  content:""; }

.bp3-icon-issue-closed::before{
  content:""; }

.bp3-icon-issue-new::before{
  content:""; }

.bp3-icon-italic::before{
  content:""; }

.bp3-icon-join-table::before{
  content:""; }

.bp3-icon-key::before{
  content:""; }

.bp3-icon-key-backspace::before{
  content:""; }

.bp3-icon-key-command::before{
  content:""; }

.bp3-icon-key-control::before{
  content:""; }

.bp3-icon-key-delete::before{
  content:""; }

.bp3-icon-key-enter::before{
  content:""; }

.bp3-icon-key-escape::before{
  content:""; }

.bp3-icon-key-option::before{
  content:""; }

.bp3-icon-key-shift::before{
  content:""; }

.bp3-icon-key-tab::before{
  content:""; }

.bp3-icon-known-vehicle::before{
  content:""; }

.bp3-icon-label::before{
  content:""; }

.bp3-icon-layer::before{
  content:""; }

.bp3-icon-layers::before{
  content:""; }

.bp3-icon-layout::before{
  content:""; }

.bp3-icon-layout-auto::before{
  content:""; }

.bp3-icon-layout-balloon::before{
  content:""; }

.bp3-icon-layout-circle::before{
  content:""; }

.bp3-icon-layout-grid::before{
  content:""; }

.bp3-icon-layout-group-by::before{
  content:""; }

.bp3-icon-layout-hierarchy::before{
  content:""; }

.bp3-icon-layout-linear::before{
  content:""; }

.bp3-icon-layout-skew-grid::before{
  content:""; }

.bp3-icon-layout-sorted-clusters::before{
  content:""; }

.bp3-icon-learning::before{
  content:""; }

.bp3-icon-left-join::before{
  content:""; }

.bp3-icon-less-than::before{
  content:""; }

.bp3-icon-less-than-or-equal-to::before{
  content:""; }

.bp3-icon-lifesaver::before{
  content:""; }

.bp3-icon-lightbulb::before{
  content:""; }

.bp3-icon-link::before{
  content:""; }

.bp3-icon-list::before{
  content:"☰"; }

.bp3-icon-list-columns::before{
  content:""; }

.bp3-icon-list-detail-view::before{
  content:""; }

.bp3-icon-locate::before{
  content:""; }

.bp3-icon-lock::before{
  content:""; }

.bp3-icon-log-in::before{
  content:""; }

.bp3-icon-log-out::before{
  content:""; }

.bp3-icon-manual::before{
  content:""; }

.bp3-icon-manually-entered-data::before{
  content:""; }

.bp3-icon-map::before{
  content:""; }

.bp3-icon-map-create::before{
  content:""; }

.bp3-icon-map-marker::before{
  content:""; }

.bp3-icon-maximize::before{
  content:""; }

.bp3-icon-media::before{
  content:""; }

.bp3-icon-menu::before{
  content:""; }

.bp3-icon-menu-closed::before{
  content:""; }

.bp3-icon-menu-open::before{
  content:""; }

.bp3-icon-merge-columns::before{
  content:""; }

.bp3-icon-merge-links::before{
  content:""; }

.bp3-icon-minimize::before{
  content:""; }

.bp3-icon-minus::before{
  content:"−"; }

.bp3-icon-mobile-phone::before{
  content:""; }

.bp3-icon-mobile-video::before{
  content:""; }

.bp3-icon-moon::before{
  content:""; }

.bp3-icon-more::before{
  content:""; }

.bp3-icon-mountain::before{
  content:""; }

.bp3-icon-move::before{
  content:""; }

.bp3-icon-mugshot::before{
  content:""; }

.bp3-icon-multi-select::before{
  content:""; }

.bp3-icon-music::before{
  content:""; }

.bp3-icon-new-drawing::before{
  content:""; }

.bp3-icon-new-grid-item::before{
  content:""; }

.bp3-icon-new-layer::before{
  content:""; }

.bp3-icon-new-layers::before{
  content:""; }

.bp3-icon-new-link::before{
  content:""; }

.bp3-icon-new-object::before{
  content:""; }

.bp3-icon-new-person::before{
  content:""; }

.bp3-icon-new-prescription::before{
  content:""; }

.bp3-icon-new-text-box::before{
  content:""; }

.bp3-icon-ninja::before{
  content:""; }

.bp3-icon-not-equal-to::before{
  content:""; }

.bp3-icon-notifications::before{
  content:""; }

.bp3-icon-notifications-updated::before{
  content:""; }

.bp3-icon-numbered-list::before{
  content:""; }

.bp3-icon-numerical::before{
  content:""; }

.bp3-icon-office::before{
  content:""; }

.bp3-icon-offline::before{
  content:""; }

.bp3-icon-oil-field::before{
  content:""; }

.bp3-icon-one-column::before{
  content:""; }

.bp3-icon-outdated::before{
  content:""; }

.bp3-icon-page-layout::before{
  content:""; }

.bp3-icon-panel-stats::before{
  content:""; }

.bp3-icon-panel-table::before{
  content:""; }

.bp3-icon-paperclip::before{
  content:""; }

.bp3-icon-paragraph::before{
  content:""; }

.bp3-icon-path::before{
  content:""; }

.bp3-icon-path-search::before{
  content:""; }

.bp3-icon-pause::before{
  content:""; }

.bp3-icon-people::before{
  content:""; }

.bp3-icon-percentage::before{
  content:""; }

.bp3-icon-person::before{
  content:""; }

.bp3-icon-phone::before{
  content:"☎"; }

.bp3-icon-pie-chart::before{
  content:""; }

.bp3-icon-pin::before{
  content:""; }

.bp3-icon-pivot::before{
  content:""; }

.bp3-icon-pivot-table::before{
  content:""; }

.bp3-icon-play::before{
  content:""; }

.bp3-icon-plus::before{
  content:"+"; }

.bp3-icon-polygon-filter::before{
  content:""; }

.bp3-icon-power::before{
  content:""; }

.bp3-icon-predictive-analysis::before{
  content:""; }

.bp3-icon-prescription::before{
  content:""; }

.bp3-icon-presentation::before{
  content:""; }

.bp3-icon-print::before{
  content:"⎙"; }

.bp3-icon-projects::before{
  content:""; }

.bp3-icon-properties::before{
  content:""; }

.bp3-icon-property::before{
  content:""; }

.bp3-icon-publish-function::before{
  content:""; }

.bp3-icon-pulse::before{
  content:""; }

.bp3-icon-random::before{
  content:""; }

.bp3-icon-record::before{
  content:""; }

.bp3-icon-redo::before{
  content:""; }

.bp3-icon-refresh::before{
  content:""; }

.bp3-icon-regression-chart::before{
  content:""; }

.bp3-icon-remove::before{
  content:""; }

.bp3-icon-remove-column::before{
  content:""; }

.bp3-icon-remove-column-left::before{
  content:""; }

.bp3-icon-remove-column-right::before{
  content:""; }

.bp3-icon-remove-row-bottom::before{
  content:""; }

.bp3-icon-remove-row-top::before{
  content:""; }

.bp3-icon-repeat::before{
  content:""; }

.bp3-icon-reset::before{
  content:""; }

.bp3-icon-resolve::before{
  content:""; }

.bp3-icon-rig::before{
  content:""; }

.bp3-icon-right-join::before{
  content:""; }

.bp3-icon-ring::before{
  content:""; }

.bp3-icon-rotate-document::before{
  content:""; }

.bp3-icon-rotate-page::before{
  content:""; }

.bp3-icon-satellite::before{
  content:""; }

.bp3-icon-saved::before{
  content:""; }

.bp3-icon-scatter-plot::before{
  content:""; }

.bp3-icon-search::before{
  content:""; }

.bp3-icon-search-around::before{
  content:""; }

.bp3-icon-search-template::before{
  content:""; }

.bp3-icon-search-text::before{
  content:""; }

.bp3-icon-segmented-control::before{
  content:""; }

.bp3-icon-select::before{
  content:""; }

.bp3-icon-selection::before{
  content:"⦿"; }

.bp3-icon-send-to::before{
  content:""; }

.bp3-icon-send-to-graph::before{
  content:""; }

.bp3-icon-send-to-map::before{
  content:""; }

.bp3-icon-series-add::before{
  content:""; }

.bp3-icon-series-configuration::before{
  content:""; }

.bp3-icon-series-derived::before{
  content:""; }

.bp3-icon-series-filtered::before{
  content:""; }

.bp3-icon-series-search::before{
  content:""; }

.bp3-icon-settings::before{
  content:""; }

.bp3-icon-share::before{
  content:""; }

.bp3-icon-shield::before{
  content:""; }

.bp3-icon-shop::before{
  content:""; }

.bp3-icon-shopping-cart::before{
  content:""; }

.bp3-icon-signal-search::before{
  content:""; }

.bp3-icon-sim-card::before{
  content:""; }

.bp3-icon-slash::before{
  content:""; }

.bp3-icon-small-cross::before{
  content:""; }

.bp3-icon-small-minus::before{
  content:""; }

.bp3-icon-small-plus::before{
  content:""; }

.bp3-icon-small-tick::before{
  content:""; }

.bp3-icon-snowflake::before{
  content:""; }

.bp3-icon-social-media::before{
  content:""; }

.bp3-icon-sort::before{
  content:""; }

.bp3-icon-sort-alphabetical::before{
  content:""; }

.bp3-icon-sort-alphabetical-desc::before{
  content:""; }

.bp3-icon-sort-asc::before{
  content:""; }

.bp3-icon-sort-desc::before{
  content:""; }

.bp3-icon-sort-numerical::before{
  content:""; }

.bp3-icon-sort-numerical-desc::before{
  content:""; }

.bp3-icon-split-columns::before{
  content:""; }

.bp3-icon-square::before{
  content:""; }

.bp3-icon-stacked-chart::before{
  content:""; }

.bp3-icon-star::before{
  content:"★"; }

.bp3-icon-star-empty::before{
  content:"☆"; }

.bp3-icon-step-backward::before{
  content:""; }

.bp3-icon-step-chart::before{
  content:""; }

.bp3-icon-step-forward::before{
  content:""; }

.bp3-icon-stop::before{
  content:""; }

.bp3-icon-stopwatch::before{
  content:""; }

.bp3-icon-strikethrough::before{
  content:""; }

.bp3-icon-style::before{
  content:""; }

.bp3-icon-swap-horizontal::before{
  content:""; }

.bp3-icon-swap-vertical::before{
  content:""; }

.bp3-icon-symbol-circle::before{
  content:""; }

.bp3-icon-symbol-cross::before{
  content:""; }

.bp3-icon-symbol-diamond::before{
  content:""; }

.bp3-icon-symbol-square::before{
  content:""; }

.bp3-icon-symbol-triangle-down::before{
  content:""; }

.bp3-icon-symbol-triangle-up::before{
  content:""; }

.bp3-icon-tag::before{
  content:""; }

.bp3-icon-take-action::before{
  content:""; }

.bp3-icon-taxi::before{
  content:""; }

.bp3-icon-text-highlight::before{
  content:""; }

.bp3-icon-th::before{
  content:""; }

.bp3-icon-th-derived::before{
  content:""; }

.bp3-icon-th-disconnect::before{
  content:""; }

.bp3-icon-th-filtered::before{
  content:""; }

.bp3-icon-th-list::before{
  content:""; }

.bp3-icon-thumbs-down::before{
  content:""; }

.bp3-icon-thumbs-up::before{
  content:""; }

.bp3-icon-tick::before{
  content:"✓"; }

.bp3-icon-tick-circle::before{
  content:""; }

.bp3-icon-time::before{
  content:"⏲"; }

.bp3-icon-timeline-area-chart::before{
  content:""; }

.bp3-icon-timeline-bar-chart::before{
  content:""; }

.bp3-icon-timeline-events::before{
  content:""; }

.bp3-icon-timeline-line-chart::before{
  content:""; }

.bp3-icon-tint::before{
  content:""; }

.bp3-icon-torch::before{
  content:""; }

.bp3-icon-tractor::before{
  content:""; }

.bp3-icon-train::before{
  content:""; }

.bp3-icon-translate::before{
  content:""; }

.bp3-icon-trash::before{
  content:""; }

.bp3-icon-tree::before{
  content:""; }

.bp3-icon-trending-down::before{
  content:""; }

.bp3-icon-trending-up::before{
  content:""; }

.bp3-icon-truck::before{
  content:""; }

.bp3-icon-two-columns::before{
  content:""; }

.bp3-icon-unarchive::before{
  content:""; }

.bp3-icon-underline::before{
  content:"⎁"; }

.bp3-icon-undo::before{
  content:"⎌"; }

.bp3-icon-ungroup-objects::before{
  content:""; }

.bp3-icon-unknown-vehicle::before{
  content:""; }

.bp3-icon-unlock::before{
  content:""; }

.bp3-icon-unpin::before{
  content:""; }

.bp3-icon-unresolve::before{
  content:""; }

.bp3-icon-updated::before{
  content:""; }

.bp3-icon-upload::before{
  content:""; }

.bp3-icon-user::before{
  content:""; }

.bp3-icon-variable::before{
  content:""; }

.bp3-icon-vertical-bar-chart-asc::before{
  content:""; }

.bp3-icon-vertical-bar-chart-desc::before{
  content:""; }

.bp3-icon-vertical-distribution::before{
  content:""; }

.bp3-icon-video::before{
  content:""; }

.bp3-icon-volume-down::before{
  content:""; }

.bp3-icon-volume-off::before{
  content:""; }

.bp3-icon-volume-up::before{
  content:""; }

.bp3-icon-walk::before{
  content:""; }

.bp3-icon-warning-sign::before{
  content:""; }

.bp3-icon-waterfall-chart::before{
  content:""; }

.bp3-icon-widget::before{
  content:""; }

.bp3-icon-widget-button::before{
  content:""; }

.bp3-icon-widget-footer::before{
  content:""; }

.bp3-icon-widget-header::before{
  content:""; }

.bp3-icon-wrench::before{
  content:""; }

.bp3-icon-zoom-in::before{
  content:""; }

.bp3-icon-zoom-out::before{
  content:""; }

.bp3-icon-zoom-to-fit::before{
  content:""; }
.bp3-submenu > .bp3-popover-wrapper{
  display:block; }

.bp3-submenu .bp3-popover-target{
  display:block; }

.bp3-submenu.bp3-popover{
  -webkit-box-shadow:none;
          box-shadow:none;
  padding:0 5px; }
  .bp3-submenu.bp3-popover > .bp3-popover-content{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-submenu.bp3-popover, .bp3-submenu.bp3-popover.bp3-dark{
    -webkit-box-shadow:none;
            box-shadow:none; }
    .bp3-dark .bp3-submenu.bp3-popover > .bp3-popover-content, .bp3-submenu.bp3-popover.bp3-dark > .bp3-popover-content{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
.bp3-menu{
  margin:0;
  border-radius:3px;
  background:#ffffff;
  min-width:180px;
  padding:5px;
  list-style:none;
  text-align:left;
  color:#182026; }

.bp3-menu-divider{
  display:block;
  margin:5px;
  border-top:1px solid rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-menu-divider{
    border-top-color:rgba(255, 255, 255, 0.15); }

.bp3-menu-item{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  border-radius:2px;
  padding:5px 7px;
  text-decoration:none;
  line-height:20px;
  color:inherit;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-menu-item > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-menu-item > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-menu-item::before,
  .bp3-menu-item > *{
    margin-right:7px; }
  .bp3-menu-item:empty::before,
  .bp3-menu-item > :last-child{
    margin-right:0; }
  .bp3-menu-item > .bp3-fill{
    word-break:break-word; }
  .bp3-menu-item:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
    background-color:rgba(167, 182, 194, 0.3);
    cursor:pointer;
    text-decoration:none; }
  .bp3-menu-item.bp3-disabled{
    background-color:inherit;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-dark .bp3-menu-item{
    color:inherit; }
    .bp3-dark .bp3-menu-item:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
      background-color:rgba(138, 155, 168, 0.15);
      color:inherit; }
    .bp3-dark .bp3-menu-item.bp3-disabled{
      background-color:inherit;
      color:rgba(167, 182, 194, 0.6); }
  .bp3-menu-item.bp3-intent-primary{
    color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-primary::before, .bp3-menu-item.bp3-intent-primary::after,
    .bp3-menu-item.bp3-intent-primary .bp3-menu-item-label{
      color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-menu-item.bp3-intent-primary.bp3-active{
      background-color:#137cbd; }
    .bp3-menu-item.bp3-intent-primary:active{
      background-color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-menu-item.bp3-intent-primary:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-menu-item.bp3-intent-primary:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-primary:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-primary:active, .bp3-menu-item.bp3-intent-primary:active::before, .bp3-menu-item.bp3-intent-primary:active::after,
    .bp3-menu-item.bp3-intent-primary:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-primary.bp3-active, .bp3-menu-item.bp3-intent-primary.bp3-active::before, .bp3-menu-item.bp3-intent-primary.bp3-active::after,
    .bp3-menu-item.bp3-intent-primary.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-success{
    color:#0d8050; }
    .bp3-menu-item.bp3-intent-success .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-success::before, .bp3-menu-item.bp3-intent-success::after,
    .bp3-menu-item.bp3-intent-success .bp3-menu-item-label{
      color:#0d8050; }
    .bp3-menu-item.bp3-intent-success:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-menu-item.bp3-intent-success.bp3-active{
      background-color:#0f9960; }
    .bp3-menu-item.bp3-intent-success:active{
      background-color:#0d8050; }
    .bp3-menu-item.bp3-intent-success:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-menu-item.bp3-intent-success:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-menu-item.bp3-intent-success:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-success:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-success:active, .bp3-menu-item.bp3-intent-success:active::before, .bp3-menu-item.bp3-intent-success:active::after,
    .bp3-menu-item.bp3-intent-success:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-success.bp3-active, .bp3-menu-item.bp3-intent-success.bp3-active::before, .bp3-menu-item.bp3-intent-success.bp3-active::after,
    .bp3-menu-item.bp3-intent-success.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-warning{
    color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-warning::before, .bp3-menu-item.bp3-intent-warning::after,
    .bp3-menu-item.bp3-intent-warning .bp3-menu-item-label{
      color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-menu-item.bp3-intent-warning.bp3-active{
      background-color:#d9822b; }
    .bp3-menu-item.bp3-intent-warning:active{
      background-color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-menu-item.bp3-intent-warning:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-menu-item.bp3-intent-warning:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-warning:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-warning:active, .bp3-menu-item.bp3-intent-warning:active::before, .bp3-menu-item.bp3-intent-warning:active::after,
    .bp3-menu-item.bp3-intent-warning:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-warning.bp3-active, .bp3-menu-item.bp3-intent-warning.bp3-active::before, .bp3-menu-item.bp3-intent-warning.bp3-active::after,
    .bp3-menu-item.bp3-intent-warning.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-danger{
    color:#c23030; }
    .bp3-menu-item.bp3-intent-danger .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-danger::before, .bp3-menu-item.bp3-intent-danger::after,
    .bp3-menu-item.bp3-intent-danger .bp3-menu-item-label{
      color:#c23030; }
    .bp3-menu-item.bp3-intent-danger:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-menu-item.bp3-intent-danger.bp3-active{
      background-color:#db3737; }
    .bp3-menu-item.bp3-intent-danger:active{
      background-color:#c23030; }
    .bp3-menu-item.bp3-intent-danger:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-menu-item.bp3-intent-danger:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-menu-item.bp3-intent-danger:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-danger:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-danger:active, .bp3-menu-item.bp3-intent-danger:active::before, .bp3-menu-item.bp3-intent-danger:active::after,
    .bp3-menu-item.bp3-intent-danger:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-danger.bp3-active, .bp3-menu-item.bp3-intent-danger.bp3-active::before, .bp3-menu-item.bp3-intent-danger.bp3-active::after,
    .bp3-menu-item.bp3-intent-danger.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item::before{
    line-height:1;
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-weight:400;
    font-style:normal;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    margin-right:7px; }
  .bp3-menu-item::before,
  .bp3-menu-item > .bp3-icon{
    margin-top:2px;
    color:#5c7080; }
  .bp3-menu-item .bp3-menu-item-label{
    color:#5c7080; }
  .bp3-menu-item:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
    color:inherit; }
  .bp3-menu-item.bp3-active, .bp3-menu-item:active{
    background-color:rgba(115, 134, 148, 0.3); }
  .bp3-menu-item.bp3-disabled{
    outline:none !important;
    background-color:inherit !important;
    cursor:not-allowed !important;
    color:rgba(92, 112, 128, 0.6) !important; }
    .bp3-menu-item.bp3-disabled::before,
    .bp3-menu-item.bp3-disabled > .bp3-icon,
    .bp3-menu-item.bp3-disabled .bp3-menu-item-label{
      color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-large .bp3-menu-item{
    padding:9px 7px;
    line-height:22px;
    font-size:16px; }
    .bp3-large .bp3-menu-item .bp3-icon{
      margin-top:3px; }
    .bp3-large .bp3-menu-item::before{
      line-height:1;
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-weight:400;
      font-style:normal;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased;
      margin-top:1px;
      margin-right:10px; }

button.bp3-menu-item{
  border:none;
  background:none;
  width:100%;
  text-align:left; }
.bp3-menu-header{
  display:block;
  margin:5px;
  border-top:1px solid rgba(16, 22, 26, 0.15);
  cursor:default;
  padding-left:2px; }
  .bp3-dark .bp3-menu-header{
    border-top-color:rgba(255, 255, 255, 0.15); }
  .bp3-menu-header:first-of-type{
    border-top:none; }
  .bp3-menu-header > h6{
    color:#182026;
    font-weight:600;
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    margin:0;
    padding:10px 7px 0 1px;
    line-height:17px; }
    .bp3-dark .bp3-menu-header > h6{
      color:#f5f8fa; }
  .bp3-menu-header:first-of-type > h6{
    padding-top:0; }
  .bp3-large .bp3-menu-header > h6{
    padding-top:15px;
    padding-bottom:5px;
    font-size:18px; }
  .bp3-large .bp3-menu-header:first-of-type > h6{
    padding-top:0; }

.bp3-dark .bp3-menu{
  background:#30404d;
  color:#f5f8fa; }

.bp3-dark .bp3-menu-item.bp3-intent-primary{
  color:#48aff0; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary::before, .bp3-dark .bp3-menu-item.bp3-intent-primary::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary .bp3-menu-item-label{
    color:#48aff0; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active{
    background-color:#137cbd; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary:active{
    background-color:#106ba3; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-primary:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-primary:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-primary:active, .bp3-dark .bp3-menu-item.bp3-intent-primary:active::before, .bp3-dark .bp3-menu-item.bp3-intent-primary:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item.bp3-intent-success{
  color:#3dcc91; }
  .bp3-dark .bp3-menu-item.bp3-intent-success .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-success::before, .bp3-dark .bp3-menu-item.bp3-intent-success::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success .bp3-menu-item-label{
    color:#3dcc91; }
  .bp3-dark .bp3-menu-item.bp3-intent-success:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active{
    background-color:#0f9960; }
  .bp3-dark .bp3-menu-item.bp3-intent-success:active{
    background-color:#0d8050; }
  .bp3-dark .bp3-menu-item.bp3-intent-success:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-success:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-success:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-success:active, .bp3-dark .bp3-menu-item.bp3-intent-success:active::before, .bp3-dark .bp3-menu-item.bp3-intent-success:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item.bp3-intent-warning{
  color:#ffb366; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning::before, .bp3-dark .bp3-menu-item.bp3-intent-warning::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning .bp3-menu-item-label{
    color:#ffb366; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active{
    background-color:#d9822b; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning:active{
    background-color:#bf7326; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-warning:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-warning:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-warning:active, .bp3-dark .bp3-menu-item.bp3-intent-warning:active::before, .bp3-dark .bp3-menu-item.bp3-intent-warning:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item.bp3-intent-danger{
  color:#ff7373; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger::before, .bp3-dark .bp3-menu-item.bp3-intent-danger::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger .bp3-menu-item-label{
    color:#ff7373; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active{
    background-color:#db3737; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger:active{
    background-color:#c23030; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-danger:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-danger:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-danger:active, .bp3-dark .bp3-menu-item.bp3-intent-danger:active::before, .bp3-dark .bp3-menu-item.bp3-intent-danger:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item::before,
.bp3-dark .bp3-menu-item > .bp3-icon{
  color:#a7b6c2; }

.bp3-dark .bp3-menu-item .bp3-menu-item-label{
  color:#a7b6c2; }

.bp3-dark .bp3-menu-item.bp3-active, .bp3-dark .bp3-menu-item:active{
  background-color:rgba(138, 155, 168, 0.3); }

.bp3-dark .bp3-menu-item.bp3-disabled{
  color:rgba(167, 182, 194, 0.6) !important; }
  .bp3-dark .bp3-menu-item.bp3-disabled::before,
  .bp3-dark .bp3-menu-item.bp3-disabled > .bp3-icon,
  .bp3-dark .bp3-menu-item.bp3-disabled .bp3-menu-item-label{
    color:rgba(167, 182, 194, 0.6) !important; }

.bp3-dark .bp3-menu-divider,
.bp3-dark .bp3-menu-header{
  border-color:rgba(255, 255, 255, 0.15); }

.bp3-dark .bp3-menu-header > h6{
  color:#f5f8fa; }

.bp3-label .bp3-menu{
  margin-top:5px; }
.bp3-navbar{
  position:relative;
  z-index:10;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  background-color:#ffffff;
  width:100%;
  height:50px;
  padding:0 15px; }
  .bp3-navbar.bp3-dark,
  .bp3-dark .bp3-navbar{
    background-color:#394b59; }
  .bp3-navbar.bp3-dark{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-navbar{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-navbar.bp3-fixed-top{
    position:fixed;
    top:0;
    right:0;
    left:0; }

.bp3-navbar-heading{
  margin-right:15px;
  font-size:16px; }

.bp3-navbar-group{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  height:50px; }
  .bp3-navbar-group.bp3-align-left{
    float:left; }
  .bp3-navbar-group.bp3-align-right{
    float:right; }

.bp3-navbar-divider{
  margin:0 10px;
  border-left:1px solid rgba(16, 22, 26, 0.15);
  height:20px; }
  .bp3-dark .bp3-navbar-divider{
    border-left-color:rgba(255, 255, 255, 0.15); }
.bp3-non-ideal-state{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  width:100%;
  height:100%;
  text-align:center; }
  .bp3-non-ideal-state > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-non-ideal-state > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-non-ideal-state::before,
  .bp3-non-ideal-state > *{
    margin-bottom:20px; }
  .bp3-non-ideal-state:empty::before,
  .bp3-non-ideal-state > :last-child{
    margin-bottom:0; }
  .bp3-non-ideal-state > *{
    max-width:400px; }

.bp3-non-ideal-state-visual{
  color:rgba(92, 112, 128, 0.6);
  font-size:60px; }
  .bp3-dark .bp3-non-ideal-state-visual{
    color:rgba(167, 182, 194, 0.6); }

.bp3-overflow-list{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-wrap:nowrap;
      flex-wrap:nowrap;
  min-width:0; }

.bp3-overflow-list-spacer{
  -ms-flex-negative:1;
      flex-shrink:1;
  width:1px; }

body.bp3-overlay-open{
  overflow:hidden; }

.bp3-overlay{
  position:static;
  top:0;
  right:0;
  bottom:0;
  left:0;
  z-index:20; }
  .bp3-overlay:not(.bp3-overlay-open){
    pointer-events:none; }
  .bp3-overlay.bp3-overlay-container{
    position:fixed;
    overflow:hidden; }
    .bp3-overlay.bp3-overlay-container.bp3-overlay-inline{
      position:absolute; }
  .bp3-overlay.bp3-overlay-scroll-container{
    position:fixed;
    overflow:auto; }
    .bp3-overlay.bp3-overlay-scroll-container.bp3-overlay-inline{
      position:absolute; }
  .bp3-overlay.bp3-overlay-inline{
    display:inline;
    overflow:visible; }

.bp3-overlay-content{
  position:fixed;
  z-index:20; }
  .bp3-overlay-inline .bp3-overlay-content,
  .bp3-overlay-scroll-container .bp3-overlay-content{
    position:absolute; }

.bp3-overlay-backdrop{
  position:fixed;
  top:0;
  right:0;
  bottom:0;
  left:0;
  opacity:1;
  z-index:20;
  background-color:rgba(16, 22, 26, 0.7);
  overflow:auto;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-overlay-backdrop.bp3-overlay-enter, .bp3-overlay-backdrop.bp3-overlay-appear{
    opacity:0; }
  .bp3-overlay-backdrop.bp3-overlay-enter-active, .bp3-overlay-backdrop.bp3-overlay-appear-active{
    opacity:1;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-overlay-backdrop.bp3-overlay-exit{
    opacity:1; }
  .bp3-overlay-backdrop.bp3-overlay-exit-active{
    opacity:0;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-overlay-backdrop:focus{
    outline:none; }
  .bp3-overlay-inline .bp3-overlay-backdrop{
    position:absolute; }
.bp3-panel-stack{
  position:relative;
  overflow:hidden; }

.bp3-panel-stack-header{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-negative:0;
      flex-shrink:0;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  z-index:1;
  -webkit-box-shadow:0 1px rgba(16, 22, 26, 0.15);
          box-shadow:0 1px rgba(16, 22, 26, 0.15);
  height:30px; }
  .bp3-dark .bp3-panel-stack-header{
    -webkit-box-shadow:0 1px rgba(255, 255, 255, 0.15);
            box-shadow:0 1px rgba(255, 255, 255, 0.15); }
  .bp3-panel-stack-header > span{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-flex:1;
        -ms-flex:1;
            flex:1;
    -webkit-box-align:stretch;
        -ms-flex-align:stretch;
            align-items:stretch; }
  .bp3-panel-stack-header .bp3-heading{
    margin:0 5px; }

.bp3-button.bp3-panel-stack-header-back{
  margin-left:5px;
  padding-left:0;
  white-space:nowrap; }
  .bp3-button.bp3-panel-stack-header-back .bp3-icon{
    margin:0 2px; }

.bp3-panel-stack-view{
  position:absolute;
  top:0;
  right:0;
  bottom:0;
  left:0;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin-right:-1px;
  border-right:1px solid rgba(16, 22, 26, 0.15);
  background-color:#ffffff;
  overflow-y:auto; }
  .bp3-dark .bp3-panel-stack-view{
    background-color:#30404d; }

.bp3-panel-stack-push .bp3-panel-stack-enter, .bp3-panel-stack-push .bp3-panel-stack-appear{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0; }

.bp3-panel-stack-push .bp3-panel-stack-enter-active, .bp3-panel-stack-push .bp3-panel-stack-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }

.bp3-panel-stack-push .bp3-panel-stack-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack-push .bp3-panel-stack-exit-active{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }

.bp3-panel-stack-pop .bp3-panel-stack-enter, .bp3-panel-stack-pop .bp3-panel-stack-appear{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0; }

.bp3-panel-stack-pop .bp3-panel-stack-enter-active, .bp3-panel-stack-pop .bp3-panel-stack-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }

.bp3-panel-stack-pop .bp3-panel-stack-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack-pop .bp3-panel-stack-exit-active{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }
.bp3-popover{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  -webkit-transform:scale(1);
          transform:scale(1);
  display:inline-block;
  z-index:20;
  border-radius:3px; }
  .bp3-popover .bp3-popover-arrow{
    position:absolute;
    width:30px;
    height:30px; }
    .bp3-popover .bp3-popover-arrow::before{
      margin:5px;
      width:20px;
      height:20px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover{
    margin-top:-17px;
    margin-bottom:17px; }
    .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow{
      bottom:-11px; }
      .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(-90deg);
                transform:rotate(-90deg); }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover{
    margin-left:17px; }
    .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow{
      left:-11px; }
      .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(0);
                transform:rotate(0); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover{
    margin-top:17px; }
    .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow{
      top:-11px; }
      .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(90deg);
                transform:rotate(90deg); }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover{
    margin-right:17px;
    margin-left:-17px; }
    .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow{
      right:-11px; }
      .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(180deg);
                transform:rotate(180deg); }
  .bp3-tether-element-attached-middle > .bp3-popover > .bp3-popover-arrow{
    top:50%;
    -webkit-transform:translateY(-50%);
            transform:translateY(-50%); }
  .bp3-tether-element-attached-center > .bp3-popover > .bp3-popover-arrow{
    right:50%;
    -webkit-transform:translateX(50%);
            transform:translateX(50%); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow{
    top:-0.3934px; }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow{
    right:-0.3934px; }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow{
    left:-0.3934px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow{
    bottom:-0.3934px; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:top left;
            transform-origin:top left; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:top center;
            transform-origin:top center; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:top right;
            transform-origin:top right; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:center left;
            transform-origin:center left; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:center center;
            transform-origin:center center; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:center right;
            transform-origin:center right; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:bottom left;
            transform-origin:bottom left; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:bottom center;
            transform-origin:bottom center; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:bottom right;
            transform-origin:bottom right; }
  .bp3-popover .bp3-popover-content{
    background:#ffffff;
    color:inherit; }
  .bp3-popover .bp3-popover-arrow::before{
    -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2);
            box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2); }
  .bp3-popover .bp3-popover-arrow-border{
    fill:#10161a;
    fill-opacity:0.1; }
  .bp3-popover .bp3-popover-arrow-fill{
    fill:#ffffff; }
  .bp3-popover-enter > .bp3-popover, .bp3-popover-appear > .bp3-popover{
    -webkit-transform:scale(0.3);
            transform:scale(0.3); }
  .bp3-popover-enter-active > .bp3-popover, .bp3-popover-appear-active > .bp3-popover{
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-popover-exit > .bp3-popover{
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-popover-exit-active > .bp3-popover{
    -webkit-transform:scale(0.3);
            transform:scale(0.3);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-popover .bp3-popover-content{
    position:relative;
    border-radius:3px; }
  .bp3-popover.bp3-popover-content-sizing .bp3-popover-content{
    max-width:350px;
    padding:20px; }
  .bp3-popover-target + .bp3-overlay .bp3-popover.bp3-popover-content-sizing{
    width:350px; }
  .bp3-popover.bp3-minimal{
    margin:0 !important; }
    .bp3-popover.bp3-minimal .bp3-popover-arrow{
      display:none; }
    .bp3-popover.bp3-minimal.bp3-popover{
      -webkit-transform:scale(1);
              transform:scale(1); }
      .bp3-popover-enter > .bp3-popover.bp3-minimal.bp3-popover, .bp3-popover-appear > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1); }
      .bp3-popover-enter-active > .bp3-popover.bp3-minimal.bp3-popover, .bp3-popover-appear-active > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1);
        -webkit-transition-property:-webkit-transform;
        transition-property:-webkit-transform;
        transition-property:transform;
        transition-property:transform, -webkit-transform;
        -webkit-transition-duration:100ms;
                transition-duration:100ms;
        -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
                transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
        -webkit-transition-delay:0;
                transition-delay:0; }
      .bp3-popover-exit > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1); }
      .bp3-popover-exit-active > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1);
        -webkit-transition-property:-webkit-transform;
        transition-property:-webkit-transform;
        transition-property:transform;
        transition-property:transform, -webkit-transform;
        -webkit-transition-duration:100ms;
                transition-duration:100ms;
        -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
                transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
        -webkit-transition-delay:0;
                transition-delay:0; }
  .bp3-popover.bp3-dark,
  .bp3-dark .bp3-popover{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
    .bp3-popover.bp3-dark .bp3-popover-content,
    .bp3-dark .bp3-popover .bp3-popover-content{
      background:#30404d;
      color:inherit; }
    .bp3-popover.bp3-dark .bp3-popover-arrow::before,
    .bp3-dark .bp3-popover .bp3-popover-arrow::before{
      -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4);
              box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4); }
    .bp3-popover.bp3-dark .bp3-popover-arrow-border,
    .bp3-dark .bp3-popover .bp3-popover-arrow-border{
      fill:#10161a;
      fill-opacity:0.2; }
    .bp3-popover.bp3-dark .bp3-popover-arrow-fill,
    .bp3-dark .bp3-popover .bp3-popover-arrow-fill{
      fill:#30404d; }

.bp3-popover-arrow::before{
  display:block;
  position:absolute;
  -webkit-transform:rotate(45deg);
          transform:rotate(45deg);
  border-radius:2px;
  content:""; }

.bp3-tether-pinned .bp3-popover-arrow{
  display:none; }

.bp3-popover-backdrop{
  background:rgba(255, 255, 255, 0); }

.bp3-transition-container{
  opacity:1;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  z-index:20; }
  .bp3-transition-container.bp3-popover-enter, .bp3-transition-container.bp3-popover-appear{
    opacity:0; }
  .bp3-transition-container.bp3-popover-enter-active, .bp3-transition-container.bp3-popover-appear-active{
    opacity:1;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-transition-container.bp3-popover-exit{
    opacity:1; }
  .bp3-transition-container.bp3-popover-exit-active{
    opacity:0;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-transition-container:focus{
    outline:none; }
  .bp3-transition-container.bp3-popover-leave .bp3-popover-content{
    pointer-events:none; }
  .bp3-transition-container[data-x-out-of-boundaries]{
    display:none; }

span.bp3-popover-target{
  display:inline-block; }

.bp3-popover-wrapper.bp3-fill{
  width:100%; }

.bp3-portal{
  position:absolute;
  top:0;
  right:0;
  left:0; }
@-webkit-keyframes linear-progress-bar-stripes{
  from{
    background-position:0 0; }
  to{
    background-position:30px 0; } }
@keyframes linear-progress-bar-stripes{
  from{
    background-position:0 0; }
  to{
    background-position:30px 0; } }

.bp3-progress-bar{
  display:block;
  position:relative;
  border-radius:40px;
  background:rgba(92, 112, 128, 0.2);
  width:100%;
  height:8px;
  overflow:hidden; }
  .bp3-progress-bar .bp3-progress-meter{
    position:absolute;
    border-radius:40px;
    background:linear-gradient(-45deg, rgba(255, 255, 255, 0.2) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.2) 50%, rgba(255, 255, 255, 0.2) 75%, transparent 75%);
    background-color:rgba(92, 112, 128, 0.8);
    background-size:30px 30px;
    width:100%;
    height:100%;
    -webkit-transition:width 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:width 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-progress-bar:not(.bp3-no-animation):not(.bp3-no-stripes) .bp3-progress-meter{
    animation:linear-progress-bar-stripes 300ms linear infinite reverse; }
  .bp3-progress-bar.bp3-no-stripes .bp3-progress-meter{
    background-image:none; }

.bp3-dark .bp3-progress-bar{
  background:rgba(16, 22, 26, 0.5); }
  .bp3-dark .bp3-progress-bar .bp3-progress-meter{
    background-color:#8a9ba8; }

.bp3-progress-bar.bp3-intent-primary .bp3-progress-meter{
  background-color:#137cbd; }

.bp3-progress-bar.bp3-intent-success .bp3-progress-meter{
  background-color:#0f9960; }

.bp3-progress-bar.bp3-intent-warning .bp3-progress-meter{
  background-color:#d9822b; }

.bp3-progress-bar.bp3-intent-danger .bp3-progress-meter{
  background-color:#db3737; }
@-webkit-keyframes skeleton-glow{
  from{
    border-color:rgba(206, 217, 224, 0.2);
    background:rgba(206, 217, 224, 0.2); }
  to{
    border-color:rgba(92, 112, 128, 0.2);
    background:rgba(92, 112, 128, 0.2); } }
@keyframes skeleton-glow{
  from{
    border-color:rgba(206, 217, 224, 0.2);
    background:rgba(206, 217, 224, 0.2); }
  to{
    border-color:rgba(92, 112, 128, 0.2);
    background:rgba(92, 112, 128, 0.2); } }
.bp3-skeleton{
  border-color:rgba(206, 217, 224, 0.2) !important;
  border-radius:2px;
  -webkit-box-shadow:none !important;
          box-shadow:none !important;
  background:rgba(206, 217, 224, 0.2);
  background-clip:padding-box !important;
  cursor:default;
  color:transparent !important;
  -webkit-animation:1000ms linear infinite alternate skeleton-glow;
          animation:1000ms linear infinite alternate skeleton-glow;
  pointer-events:none;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-skeleton::before, .bp3-skeleton::after,
  .bp3-skeleton *{
    visibility:hidden !important; }
.bp3-slider{
  width:100%;
  min-width:150px;
  height:40px;
  position:relative;
  outline:none;
  cursor:default;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-slider:hover{
    cursor:pointer; }
  .bp3-slider:active{
    cursor:-webkit-grabbing;
    cursor:grabbing; }
  .bp3-slider.bp3-disabled{
    opacity:0.5;
    cursor:not-allowed; }
  .bp3-slider.bp3-slider-unlabeled{
    height:16px; }

.bp3-slider-track,
.bp3-slider-progress{
  top:5px;
  right:0;
  left:0;
  height:6px;
  position:absolute; }

.bp3-slider-track{
  border-radius:3px;
  overflow:hidden; }

.bp3-slider-progress{
  background:rgba(92, 112, 128, 0.2); }
  .bp3-dark .bp3-slider-progress{
    background:rgba(16, 22, 26, 0.5); }
  .bp3-slider-progress.bp3-intent-primary{
    background-color:#137cbd; }
  .bp3-slider-progress.bp3-intent-success{
    background-color:#0f9960; }
  .bp3-slider-progress.bp3-intent-warning{
    background-color:#d9822b; }
  .bp3-slider-progress.bp3-intent-danger{
    background-color:#db3737; }

.bp3-slider-handle{
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
  background-color:#f5f8fa;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
  color:#182026;
  position:absolute;
  top:0;
  left:0;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
  cursor:pointer;
  width:16px;
  height:16px; }
  .bp3-slider-handle:hover{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5; }
  .bp3-slider-handle:active, .bp3-slider-handle.bp3-active{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none; }
  .bp3-slider-handle:disabled, .bp3-slider-handle.bp3-disabled{
    outline:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    background-color:rgba(206, 217, 224, 0.5);
    background-image:none;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
    .bp3-slider-handle:disabled.bp3-active, .bp3-slider-handle:disabled.bp3-active:hover, .bp3-slider-handle.bp3-disabled.bp3-active, .bp3-slider-handle.bp3-disabled.bp3-active:hover{
      background:rgba(206, 217, 224, 0.7); }
  .bp3-slider-handle:focus{
    z-index:1; }
  .bp3-slider-handle:hover{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5;
    z-index:2;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
    cursor:-webkit-grab;
    cursor:grab; }
  .bp3-slider-handle.bp3-active{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 1px rgba(16, 22, 26, 0.1);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 1px rgba(16, 22, 26, 0.1);
    cursor:-webkit-grabbing;
    cursor:grabbing; }
  .bp3-disabled .bp3-slider-handle{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:#bfccd6;
    pointer-events:none; }
  .bp3-dark .bp3-slider-handle{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#394b59;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
    color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle:hover, .bp3-dark .bp3-slider-handle:active, .bp3-dark .bp3-slider-handle.bp3-active{
      color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle:hover{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#30404d; }
    .bp3-dark .bp3-slider-handle:active, .bp3-dark .bp3-slider-handle.bp3-active{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#202b33;
      background-image:none; }
    .bp3-dark .bp3-slider-handle:disabled, .bp3-dark .bp3-slider-handle.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(57, 75, 89, 0.5);
      background-image:none;
      color:rgba(167, 182, 194, 0.6); }
      .bp3-dark .bp3-slider-handle:disabled.bp3-active, .bp3-dark .bp3-slider-handle.bp3-disabled.bp3-active{
        background:rgba(57, 75, 89, 0.7); }
    .bp3-dark .bp3-slider-handle .bp3-button-spinner .bp3-spinner-head{
      background:rgba(16, 22, 26, 0.5);
      stroke:#8a9ba8; }
    .bp3-dark .bp3-slider-handle, .bp3-dark .bp3-slider-handle:hover{
      background-color:#394b59; }
    .bp3-dark .bp3-slider-handle.bp3-active{
      background-color:#293742; }
  .bp3-dark .bp3-disabled .bp3-slider-handle{
    border-color:#5c7080;
    -webkit-box-shadow:none;
            box-shadow:none;
    background:#5c7080; }
  .bp3-slider-handle .bp3-slider-label{
    margin-left:8px;
    border-radius:3px;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
    background:#394b59;
    color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle .bp3-slider-label{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
      background:#e1e8ed;
      color:#394b59; }
    .bp3-disabled .bp3-slider-handle .bp3-slider-label{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-slider-handle.bp3-start, .bp3-slider-handle.bp3-end{
    width:8px; }
  .bp3-slider-handle.bp3-start{
    border-top-right-radius:0;
    border-bottom-right-radius:0; }
  .bp3-slider-handle.bp3-end{
    margin-left:8px;
    border-top-left-radius:0;
    border-bottom-left-radius:0; }
    .bp3-slider-handle.bp3-end .bp3-slider-label{
      margin-left:0; }

.bp3-slider-label{
  -webkit-transform:translate(-50%, 20px);
          transform:translate(-50%, 20px);
  display:inline-block;
  position:absolute;
  padding:2px 5px;
  vertical-align:top;
  line-height:1;
  font-size:12px; }

.bp3-slider.bp3-vertical{
  width:40px;
  min-width:40px;
  height:150px; }
  .bp3-slider.bp3-vertical .bp3-slider-track,
  .bp3-slider.bp3-vertical .bp3-slider-progress{
    top:0;
    bottom:0;
    left:5px;
    width:6px;
    height:auto; }
  .bp3-slider.bp3-vertical .bp3-slider-progress{
    top:auto; }
  .bp3-slider.bp3-vertical .bp3-slider-label{
    -webkit-transform:translate(20px, 50%);
            transform:translate(20px, 50%); }
  .bp3-slider.bp3-vertical .bp3-slider-handle{
    top:auto; }
    .bp3-slider.bp3-vertical .bp3-slider-handle .bp3-slider-label{
      margin-top:-8px;
      margin-left:0; }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-end, .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start{
      margin-left:0;
      width:16px;
      height:8px; }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start{
      border-top-left-radius:0;
      border-bottom-right-radius:3px; }
      .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start .bp3-slider-label{
        -webkit-transform:translate(20px);
                transform:translate(20px); }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-end{
      margin-bottom:8px;
      border-top-left-radius:3px;
      border-bottom-left-radius:0;
      border-bottom-right-radius:0; }

@-webkit-keyframes pt-spinner-animation{
  from{
    -webkit-transform:rotate(0deg);
            transform:rotate(0deg); }
  to{
    -webkit-transform:rotate(360deg);
            transform:rotate(360deg); } }

@keyframes pt-spinner-animation{
  from{
    -webkit-transform:rotate(0deg);
            transform:rotate(0deg); }
  to{
    -webkit-transform:rotate(360deg);
            transform:rotate(360deg); } }

.bp3-spinner{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  overflow:visible;
  vertical-align:middle; }
  .bp3-spinner svg{
    display:block; }
  .bp3-spinner path{
    fill-opacity:0; }
  .bp3-spinner .bp3-spinner-head{
    -webkit-transform-origin:center;
            transform-origin:center;
    -webkit-transition:stroke-dashoffset 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:stroke-dashoffset 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    stroke:rgba(92, 112, 128, 0.8);
    stroke-linecap:round; }
  .bp3-spinner .bp3-spinner-track{
    stroke:rgba(92, 112, 128, 0.2); }

.bp3-spinner-animation{
  -webkit-animation:pt-spinner-animation 500ms linear infinite;
          animation:pt-spinner-animation 500ms linear infinite; }
  .bp3-no-spin > .bp3-spinner-animation{
    -webkit-animation:none;
            animation:none; }

.bp3-dark .bp3-spinner .bp3-spinner-head{
  stroke:#8a9ba8; }

.bp3-dark .bp3-spinner .bp3-spinner-track{
  stroke:rgba(16, 22, 26, 0.5); }

.bp3-spinner.bp3-intent-primary .bp3-spinner-head{
  stroke:#137cbd; }

.bp3-spinner.bp3-intent-success .bp3-spinner-head{
  stroke:#0f9960; }

.bp3-spinner.bp3-intent-warning .bp3-spinner-head{
  stroke:#d9822b; }

.bp3-spinner.bp3-intent-danger .bp3-spinner-head{
  stroke:#db3737; }
.bp3-tabs.bp3-vertical{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex; }
  .bp3-tabs.bp3-vertical > .bp3-tab-list{
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column;
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start; }
    .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab{
      border-radius:3px;
      width:100%;
      padding:0 10px; }
      .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab[aria-selected="true"]{
        -webkit-box-shadow:none;
                box-shadow:none;
        background-color:rgba(19, 124, 189, 0.2); }
    .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab-indicator-wrapper .bp3-tab-indicator{
      top:0;
      right:0;
      bottom:0;
      left:0;
      border-radius:3px;
      background-color:rgba(19, 124, 189, 0.2);
      height:auto; }
  .bp3-tabs.bp3-vertical > .bp3-tab-panel{
    margin-top:0;
    padding-left:20px; }

.bp3-tab-list{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  -webkit-box-align:end;
      -ms-flex-align:end;
          align-items:flex-end;
  position:relative;
  margin:0;
  border:none;
  padding:0;
  list-style:none; }
  .bp3-tab-list > *:not(:last-child){
    margin-right:20px; }

.bp3-tab{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  position:relative;
  cursor:pointer;
  max-width:100%;
  vertical-align:top;
  line-height:30px;
  color:#182026;
  font-size:14px; }
  .bp3-tab a{
    display:block;
    text-decoration:none;
    color:inherit; }
  .bp3-tab-indicator-wrapper ~ .bp3-tab{
    -webkit-box-shadow:none !important;
            box-shadow:none !important;
    background-color:transparent !important; }
  .bp3-tab[aria-disabled="true"]{
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-tab[aria-selected="true"]{
    border-radius:0;
    -webkit-box-shadow:inset 0 -3px 0 #106ba3;
            box-shadow:inset 0 -3px 0 #106ba3; }
  .bp3-tab[aria-selected="true"], .bp3-tab:not([aria-disabled="true"]):hover{
    color:#106ba3; }
  .bp3-tab:focus{
    -moz-outline-radius:0; }
  .bp3-large > .bp3-tab{
    line-height:40px;
    font-size:16px; }

.bp3-tab-panel{
  margin-top:20px; }
  .bp3-tab-panel[aria-hidden="true"]{
    display:none; }

.bp3-tab-indicator-wrapper{
  position:absolute;
  top:0;
  left:0;
  -webkit-transform:translateX(0), translateY(0);
          transform:translateX(0), translateY(0);
  -webkit-transition:height, width, -webkit-transform;
  transition:height, width, -webkit-transform;
  transition:height, transform, width;
  transition:height, transform, width, -webkit-transform;
  -webkit-transition-duration:200ms;
          transition-duration:200ms;
  -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
          transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
  pointer-events:none; }
  .bp3-tab-indicator-wrapper .bp3-tab-indicator{
    position:absolute;
    right:0;
    bottom:0;
    left:0;
    background-color:#106ba3;
    height:3px; }
  .bp3-tab-indicator-wrapper.bp3-no-animation{
    -webkit-transition:none;
    transition:none; }

.bp3-dark .bp3-tab{
  color:#f5f8fa; }
  .bp3-dark .bp3-tab[aria-disabled="true"]{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-dark .bp3-tab[aria-selected="true"]{
    -webkit-box-shadow:inset 0 -3px 0 #48aff0;
            box-shadow:inset 0 -3px 0 #48aff0; }
  .bp3-dark .bp3-tab[aria-selected="true"], .bp3-dark .bp3-tab:not([aria-disabled="true"]):hover{
    color:#48aff0; }

.bp3-dark .bp3-tab-indicator{
  background-color:#48aff0; }

.bp3-flex-expander{
  -webkit-box-flex:1;
      -ms-flex:1 1;
          flex:1 1; }
.bp3-tag{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  position:relative;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:none;
          box-shadow:none;
  background-color:#5c7080;
  min-width:20px;
  max-width:100%;
  min-height:20px;
  padding:2px 6px;
  line-height:16px;
  color:#f5f8fa;
  font-size:12px; }
  .bp3-tag.bp3-interactive{
    cursor:pointer; }
    .bp3-tag.bp3-interactive:hover{
      background-color:rgba(92, 112, 128, 0.85); }
    .bp3-tag.bp3-interactive.bp3-active, .bp3-tag.bp3-interactive:active{
      background-color:rgba(92, 112, 128, 0.7); }
  .bp3-tag > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-tag > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-tag::before,
  .bp3-tag > *{
    margin-right:4px; }
  .bp3-tag:empty::before,
  .bp3-tag > :last-child{
    margin-right:0; }
  .bp3-tag:focus{
    outline:rgba(19, 124, 189, 0.6) auto 2px;
    outline-offset:0;
    -moz-outline-radius:6px; }
  .bp3-tag.bp3-round{
    border-radius:30px;
    padding-right:8px;
    padding-left:8px; }
  .bp3-dark .bp3-tag{
    background-color:#bfccd6;
    color:#182026; }
    .bp3-dark .bp3-tag.bp3-interactive{
      cursor:pointer; }
      .bp3-dark .bp3-tag.bp3-interactive:hover{
        background-color:rgba(191, 204, 214, 0.85); }
      .bp3-dark .bp3-tag.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-interactive:active{
        background-color:rgba(191, 204, 214, 0.7); }
    .bp3-dark .bp3-tag > .bp3-icon, .bp3-dark .bp3-tag .bp3-icon-standard, .bp3-dark .bp3-tag .bp3-icon-large{
      fill:currentColor; }
  .bp3-tag > .bp3-icon, .bp3-tag .bp3-icon-standard, .bp3-tag .bp3-icon-large{
    fill:#ffffff; }
  .bp3-tag.bp3-large,
  .bp3-large .bp3-tag{
    min-width:30px;
    min-height:30px;
    padding:0 10px;
    line-height:20px;
    font-size:14px; }
    .bp3-tag.bp3-large::before,
    .bp3-tag.bp3-large > *,
    .bp3-large .bp3-tag::before,
    .bp3-large .bp3-tag > *{
      margin-right:7px; }
    .bp3-tag.bp3-large:empty::before,
    .bp3-tag.bp3-large > :last-child,
    .bp3-large .bp3-tag:empty::before,
    .bp3-large .bp3-tag > :last-child{
      margin-right:0; }
    .bp3-tag.bp3-large.bp3-round,
    .bp3-large .bp3-tag.bp3-round{
      padding-right:12px;
      padding-left:12px; }
  .bp3-tag.bp3-intent-primary{
    background:#137cbd;
    color:#ffffff; }
    .bp3-tag.bp3-intent-primary.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-primary.bp3-interactive:hover{
        background-color:rgba(19, 124, 189, 0.85); }
      .bp3-tag.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-primary.bp3-interactive:active{
        background-color:rgba(19, 124, 189, 0.7); }
  .bp3-tag.bp3-intent-success{
    background:#0f9960;
    color:#ffffff; }
    .bp3-tag.bp3-intent-success.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-success.bp3-interactive:hover{
        background-color:rgba(15, 153, 96, 0.85); }
      .bp3-tag.bp3-intent-success.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-success.bp3-interactive:active{
        background-color:rgba(15, 153, 96, 0.7); }
  .bp3-tag.bp3-intent-warning{
    background:#d9822b;
    color:#ffffff; }
    .bp3-tag.bp3-intent-warning.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-warning.bp3-interactive:hover{
        background-color:rgba(217, 130, 43, 0.85); }
      .bp3-tag.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-warning.bp3-interactive:active{
        background-color:rgba(217, 130, 43, 0.7); }
  .bp3-tag.bp3-intent-danger{
    background:#db3737;
    color:#ffffff; }
    .bp3-tag.bp3-intent-danger.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-danger.bp3-interactive:hover{
        background-color:rgba(219, 55, 55, 0.85); }
      .bp3-tag.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-danger.bp3-interactive:active{
        background-color:rgba(219, 55, 55, 0.7); }
  .bp3-tag.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-tag.bp3-minimal > .bp3-icon, .bp3-tag.bp3-minimal .bp3-icon-standard, .bp3-tag.bp3-minimal .bp3-icon-large{
    fill:#5c7080; }
  .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]){
    background-color:rgba(138, 155, 168, 0.2);
    color:#182026; }
    .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:hover{
        background-color:rgba(92, 112, 128, 0.3); }
      .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive.bp3-active, .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:active{
        background-color:rgba(92, 112, 128, 0.4); }
    .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]){
      color:#f5f8fa; }
      .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:hover{
          background-color:rgba(191, 204, 214, 0.3); }
        .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:active{
          background-color:rgba(191, 204, 214, 0.4); }
      .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) > .bp3-icon, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) .bp3-icon-standard, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) .bp3-icon-large{
        fill:#a7b6c2; }
  .bp3-tag.bp3-minimal.bp3-intent-primary{
    background-color:rgba(19, 124, 189, 0.15);
    color:#106ba3; }
    .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:hover{
        background-color:rgba(19, 124, 189, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:active{
        background-color:rgba(19, 124, 189, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-primary > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-primary .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-primary .bp3-icon-large{
      fill:#137cbd; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary{
      background-color:rgba(19, 124, 189, 0.25);
      color:#48aff0; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:hover{
          background-color:rgba(19, 124, 189, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:active{
          background-color:rgba(19, 124, 189, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-success{
    background-color:rgba(15, 153, 96, 0.15);
    color:#0d8050; }
    .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:hover{
        background-color:rgba(15, 153, 96, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:active{
        background-color:rgba(15, 153, 96, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-success > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-success .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-success .bp3-icon-large{
      fill:#0f9960; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success{
      background-color:rgba(15, 153, 96, 0.25);
      color:#3dcc91; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:hover{
          background-color:rgba(15, 153, 96, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:active{
          background-color:rgba(15, 153, 96, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-warning{
    background-color:rgba(217, 130, 43, 0.15);
    color:#bf7326; }
    .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:hover{
        background-color:rgba(217, 130, 43, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:active{
        background-color:rgba(217, 130, 43, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-warning > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-warning .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-warning .bp3-icon-large{
      fill:#d9822b; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning{
      background-color:rgba(217, 130, 43, 0.25);
      color:#ffb366; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:hover{
          background-color:rgba(217, 130, 43, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:active{
          background-color:rgba(217, 130, 43, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-danger{
    background-color:rgba(219, 55, 55, 0.15);
    color:#c23030; }
    .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:hover{
        background-color:rgba(219, 55, 55, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:active{
        background-color:rgba(219, 55, 55, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-danger > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-danger .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-danger .bp3-icon-large{
      fill:#db3737; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger{
      background-color:rgba(219, 55, 55, 0.25);
      color:#ff7373; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:hover{
          background-color:rgba(219, 55, 55, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:active{
          background-color:rgba(219, 55, 55, 0.45); }

.bp3-tag-remove{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  opacity:0.5;
  margin-top:-2px;
  margin-right:-6px !important;
  margin-bottom:-2px;
  border:none;
  background:none;
  cursor:pointer;
  padding:2px;
  padding-left:0;
  color:inherit; }
  .bp3-tag-remove:hover{
    opacity:0.8;
    background:none;
    text-decoration:none; }
  .bp3-tag-remove:active{
    opacity:1; }
  .bp3-tag-remove:empty::before{
    line-height:1;
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-weight:400;
    font-style:normal;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    content:""; }
  .bp3-large .bp3-tag-remove{
    margin-right:-10px !important;
    padding:5px;
    padding-left:0; }
    .bp3-large .bp3-tag-remove:empty::before{
      line-height:1;
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-weight:400;
      font-style:normal; }
.bp3-tag-input{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  cursor:text;
  height:auto;
  min-height:30px;
  padding-right:0;
  padding-left:5px;
  line-height:inherit; }
  .bp3-tag-input > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-tag-input > .bp3-tag-input-values{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-tag-input .bp3-tag-input-icon{
    margin-top:7px;
    margin-right:7px;
    margin-left:2px;
    color:#5c7080; }
  .bp3-tag-input .bp3-tag-input-values{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-orient:horizontal;
    -webkit-box-direction:normal;
        -ms-flex-direction:row;
            flex-direction:row;
    -ms-flex-wrap:wrap;
        flex-wrap:wrap;
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center;
    -ms-flex-item-align:stretch;
        align-self:stretch;
    margin-top:5px;
    margin-right:7px;
    min-width:0; }
    .bp3-tag-input .bp3-tag-input-values > *{
      -webkit-box-flex:0;
          -ms-flex-positive:0;
              flex-grow:0;
      -ms-flex-negative:0;
          flex-shrink:0; }
    .bp3-tag-input .bp3-tag-input-values > .bp3-fill{
      -webkit-box-flex:1;
          -ms-flex-positive:1;
              flex-grow:1;
      -ms-flex-negative:1;
          flex-shrink:1; }
    .bp3-tag-input .bp3-tag-input-values::before,
    .bp3-tag-input .bp3-tag-input-values > *{
      margin-right:5px; }
    .bp3-tag-input .bp3-tag-input-values:empty::before,
    .bp3-tag-input .bp3-tag-input-values > :last-child{
      margin-right:0; }
    .bp3-tag-input .bp3-tag-input-values:first-child .bp3-input-ghost:first-child{
      padding-left:5px; }
    .bp3-tag-input .bp3-tag-input-values > *{
      margin-bottom:5px; }
  .bp3-tag-input .bp3-tag{
    overflow-wrap:break-word; }
    .bp3-tag-input .bp3-tag.bp3-active{
      outline:rgba(19, 124, 189, 0.6) auto 2px;
      outline-offset:0;
      -moz-outline-radius:6px; }
  .bp3-tag-input .bp3-input-ghost{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:80px;
    line-height:20px; }
    .bp3-tag-input .bp3-input-ghost:disabled, .bp3-tag-input .bp3-input-ghost.bp3-disabled{
      cursor:not-allowed; }
  .bp3-tag-input .bp3-button,
  .bp3-tag-input .bp3-spinner{
    margin:3px;
    margin-left:0; }
  .bp3-tag-input .bp3-button{
    min-width:24px;
    min-height:24px;
    padding:0 7px; }
  .bp3-tag-input.bp3-large{
    height:auto;
    min-height:40px; }
    .bp3-tag-input.bp3-large::before,
    .bp3-tag-input.bp3-large > *{
      margin-right:10px; }
    .bp3-tag-input.bp3-large:empty::before,
    .bp3-tag-input.bp3-large > :last-child{
      margin-right:0; }
    .bp3-tag-input.bp3-large .bp3-tag-input-icon{
      margin-top:10px;
      margin-left:5px; }
    .bp3-tag-input.bp3-large .bp3-input-ghost{
      line-height:30px; }
    .bp3-tag-input.bp3-large .bp3-button{
      min-width:30px;
      min-height:30px;
      padding:5px 10px;
      margin:5px;
      margin-left:0; }
    .bp3-tag-input.bp3-large .bp3-spinner{
      margin:8px;
      margin-left:0; }
  .bp3-tag-input.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
    background-color:#ffffff; }
    .bp3-tag-input.bp3-active.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-success{
      -webkit-box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-tag-input .bp3-tag-input-icon, .bp3-tag-input.bp3-dark .bp3-tag-input-icon{
    color:#a7b6c2; }
  .bp3-dark .bp3-tag-input .bp3-input-ghost, .bp3-tag-input.bp3-dark .bp3-input-ghost{
    color:#f5f8fa; }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-webkit-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-moz-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost:-ms-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-ms-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::placeholder{
      color:rgba(167, 182, 194, 0.6); }
  .bp3-dark .bp3-tag-input.bp3-active, .bp3-tag-input.bp3-dark.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background-color:rgba(16, 22, 26, 0.3); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-primary, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-success, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-success{
      -webkit-box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-warning, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-danger, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-input-ghost{
  border:none;
  -webkit-box-shadow:none;
          box-shadow:none;
  background:none;
  padding:0; }
  .bp3-input-ghost::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost:focus{
    outline:none !important; }
.bp3-toast{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  position:relative !important;
  margin:20px 0 0;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  background-color:#ffffff;
  min-width:300px;
  max-width:500px;
  pointer-events:all; }
  .bp3-toast.bp3-toast-enter, .bp3-toast.bp3-toast-appear{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px); }
  .bp3-toast.bp3-toast-enter-active, .bp3-toast.bp3-toast-appear-active{
    -webkit-transform:translateY(0);
            transform:translateY(0);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-toast.bp3-toast-enter ~ .bp3-toast, .bp3-toast.bp3-toast-appear ~ .bp3-toast{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px); }
  .bp3-toast.bp3-toast-enter-active ~ .bp3-toast, .bp3-toast.bp3-toast-appear-active ~ .bp3-toast{
    -webkit-transform:translateY(0);
            transform:translateY(0);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-toast.bp3-toast-exit{
    opacity:1;
    -webkit-filter:blur(0);
            filter:blur(0); }
  .bp3-toast.bp3-toast-exit-active{
    opacity:0;
    -webkit-filter:blur(10px);
            filter:blur(10px);
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:opacity, filter;
    transition-property:opacity, filter, -webkit-filter;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-toast.bp3-toast-exit ~ .bp3-toast{
    -webkit-transform:translateY(0);
            transform:translateY(0); }
  .bp3-toast.bp3-toast-exit-active ~ .bp3-toast{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:50ms;
            transition-delay:50ms; }
  .bp3-toast .bp3-button-group{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    padding:5px;
    padding-left:0; }
  .bp3-toast > .bp3-icon{
    margin:12px;
    margin-right:0;
    color:#5c7080; }
  .bp3-toast.bp3-dark,
  .bp3-dark .bp3-toast{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
    background-color:#394b59; }
    .bp3-toast.bp3-dark > .bp3-icon,
    .bp3-dark .bp3-toast > .bp3-icon{
      color:#a7b6c2; }
  .bp3-toast[class*="bp3-intent-"] a{
    color:rgba(255, 255, 255, 0.7); }
    .bp3-toast[class*="bp3-intent-"] a:hover{
      color:#ffffff; }
  .bp3-toast[class*="bp3-intent-"] > .bp3-icon{
    color:#ffffff; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button, .bp3-toast[class*="bp3-intent-"] .bp3-button::before,
  .bp3-toast[class*="bp3-intent-"] .bp3-button .bp3-icon, .bp3-toast[class*="bp3-intent-"] .bp3-button:active{
    color:rgba(255, 255, 255, 0.7) !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:focus{
    outline-color:rgba(255, 255, 255, 0.5); }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:hover{
    background-color:rgba(255, 255, 255, 0.15) !important;
    color:#ffffff !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:active{
    background-color:rgba(255, 255, 255, 0.3) !important;
    color:#ffffff !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button::after{
    background:rgba(255, 255, 255, 0.3) !important; }
  .bp3-toast.bp3-intent-primary{
    background-color:#137cbd;
    color:#ffffff; }
  .bp3-toast.bp3-intent-success{
    background-color:#0f9960;
    color:#ffffff; }
  .bp3-toast.bp3-intent-warning{
    background-color:#d9822b;
    color:#ffffff; }
  .bp3-toast.bp3-intent-danger{
    background-color:#db3737;
    color:#ffffff; }

.bp3-toast-message{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  padding:11px;
  word-break:break-word; }

.bp3-toast-container{
  display:-webkit-box !important;
  display:-ms-flexbox !important;
  display:flex !important;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  position:fixed;
  right:0;
  left:0;
  z-index:40;
  overflow:hidden;
  padding:0 20px 20px;
  pointer-events:none; }
  .bp3-toast-container.bp3-toast-container-top{
    top:0;
    bottom:auto; }
  .bp3-toast-container.bp3-toast-container-bottom{
    -webkit-box-orient:vertical;
    -webkit-box-direction:reverse;
        -ms-flex-direction:column-reverse;
            flex-direction:column-reverse;
    top:auto;
    bottom:0; }
  .bp3-toast-container.bp3-toast-container-left{
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start; }
  .bp3-toast-container.bp3-toast-container-right{
    -webkit-box-align:end;
        -ms-flex-align:end;
            align-items:flex-end; }

.bp3-toast-container-bottom .bp3-toast.bp3-toast-enter:not(.bp3-toast-enter-active),
.bp3-toast-container-bottom .bp3-toast.bp3-toast-enter:not(.bp3-toast-enter-active) ~ .bp3-toast, .bp3-toast-container-bottom .bp3-toast.bp3-toast-appear:not(.bp3-toast-appear-active),
.bp3-toast-container-bottom .bp3-toast.bp3-toast-appear:not(.bp3-toast-appear-active) ~ .bp3-toast,
.bp3-toast-container-bottom .bp3-toast.bp3-toast-leave-active ~ .bp3-toast{
  -webkit-transform:translateY(60px);
          transform:translateY(60px); }
.bp3-tooltip{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  -webkit-transform:scale(1);
          transform:scale(1); }
  .bp3-tooltip .bp3-popover-arrow{
    position:absolute;
    width:22px;
    height:22px; }
    .bp3-tooltip .bp3-popover-arrow::before{
      margin:4px;
      width:14px;
      height:14px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip{
    margin-top:-11px;
    margin-bottom:11px; }
    .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow{
      bottom:-8px; }
      .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(-90deg);
                transform:rotate(-90deg); }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip{
    margin-left:11px; }
    .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow{
      left:-8px; }
      .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(0);
                transform:rotate(0); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip{
    margin-top:11px; }
    .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow{
      top:-8px; }
      .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(90deg);
                transform:rotate(90deg); }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip{
    margin-right:11px;
    margin-left:-11px; }
    .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow{
      right:-8px; }
      .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(180deg);
                transform:rotate(180deg); }
  .bp3-tether-element-attached-middle > .bp3-tooltip > .bp3-popover-arrow{
    top:50%;
    -webkit-transform:translateY(-50%);
            transform:translateY(-50%); }
  .bp3-tether-element-attached-center > .bp3-tooltip > .bp3-popover-arrow{
    right:50%;
    -webkit-transform:translateX(50%);
            transform:translateX(50%); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow{
    top:-0.22183px; }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow{
    right:-0.22183px; }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow{
    left:-0.22183px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow{
    bottom:-0.22183px; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:top left;
            transform-origin:top left; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:top center;
            transform-origin:top center; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:top right;
            transform-origin:top right; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:center left;
            transform-origin:center left; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:center center;
            transform-origin:center center; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:center right;
            transform-origin:center right; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:bottom left;
            transform-origin:bottom left; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:bottom center;
            transform-origin:bottom center; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:bottom right;
            transform-origin:bottom right; }
  .bp3-tooltip .bp3-popover-content{
    background:#394b59;
    color:#f5f8fa; }
  .bp3-tooltip .bp3-popover-arrow::before{
    -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2);
            box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2); }
  .bp3-tooltip .bp3-popover-arrow-border{
    fill:#10161a;
    fill-opacity:0.1; }
  .bp3-tooltip .bp3-popover-arrow-fill{
    fill:#394b59; }
  .bp3-popover-enter > .bp3-tooltip, .bp3-popover-appear > .bp3-tooltip{
    -webkit-transform:scale(0.8);
            transform:scale(0.8); }
  .bp3-popover-enter-active > .bp3-tooltip, .bp3-popover-appear-active > .bp3-tooltip{
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-popover-exit > .bp3-tooltip{
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-popover-exit-active > .bp3-tooltip{
    -webkit-transform:scale(0.8);
            transform:scale(0.8);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-tooltip .bp3-popover-content{
    padding:10px 12px; }
  .bp3-tooltip.bp3-dark,
  .bp3-dark .bp3-tooltip{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
    .bp3-tooltip.bp3-dark .bp3-popover-content,
    .bp3-dark .bp3-tooltip .bp3-popover-content{
      background:#e1e8ed;
      color:#394b59; }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow::before,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow::before{
      -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4);
              box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4); }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow-border,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow-border{
      fill:#10161a;
      fill-opacity:0.2; }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow-fill,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow-fill{
      fill:#e1e8ed; }
  .bp3-tooltip.bp3-intent-primary .bp3-popover-content{
    background:#137cbd;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-primary .bp3-popover-arrow-fill{
    fill:#137cbd; }
  .bp3-tooltip.bp3-intent-success .bp3-popover-content{
    background:#0f9960;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-success .bp3-popover-arrow-fill{
    fill:#0f9960; }
  .bp3-tooltip.bp3-intent-warning .bp3-popover-content{
    background:#d9822b;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-warning .bp3-popover-arrow-fill{
    fill:#d9822b; }
  .bp3-tooltip.bp3-intent-danger .bp3-popover-content{
    background:#db3737;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-danger .bp3-popover-arrow-fill{
    fill:#db3737; }

.bp3-tooltip-indicator{
  border-bottom:dotted 1px;
  cursor:help; }
.bp3-tree .bp3-icon, .bp3-tree .bp3-icon-standard, .bp3-tree .bp3-icon-large{
  color:#5c7080; }
  .bp3-tree .bp3-icon.bp3-intent-primary, .bp3-tree .bp3-icon-standard.bp3-intent-primary, .bp3-tree .bp3-icon-large.bp3-intent-primary{
    color:#137cbd; }
  .bp3-tree .bp3-icon.bp3-intent-success, .bp3-tree .bp3-icon-standard.bp3-intent-success, .bp3-tree .bp3-icon-large.bp3-intent-success{
    color:#0f9960; }
  .bp3-tree .bp3-icon.bp3-intent-warning, .bp3-tree .bp3-icon-standard.bp3-intent-warning, .bp3-tree .bp3-icon-large.bp3-intent-warning{
    color:#d9822b; }
  .bp3-tree .bp3-icon.bp3-intent-danger, .bp3-tree .bp3-icon-standard.bp3-intent-danger, .bp3-tree .bp3-icon-large.bp3-intent-danger{
    color:#db3737; }

.bp3-tree-node-list{
  margin:0;
  padding-left:0;
  list-style:none; }

.bp3-tree-root{
  position:relative;
  background-color:transparent;
  cursor:default;
  padding-left:0; }

.bp3-tree-node-content-0{
  padding-left:0px; }

.bp3-tree-node-content-1{
  padding-left:23px; }

.bp3-tree-node-content-2{
  padding-left:46px; }

.bp3-tree-node-content-3{
  padding-left:69px; }

.bp3-tree-node-content-4{
  padding-left:92px; }

.bp3-tree-node-content-5{
  padding-left:115px; }

.bp3-tree-node-content-6{
  padding-left:138px; }

.bp3-tree-node-content-7{
  padding-left:161px; }

.bp3-tree-node-content-8{
  padding-left:184px; }

.bp3-tree-node-content-9{
  padding-left:207px; }

.bp3-tree-node-content-10{
  padding-left:230px; }

.bp3-tree-node-content-11{
  padding-left:253px; }

.bp3-tree-node-content-12{
  padding-left:276px; }

.bp3-tree-node-content-13{
  padding-left:299px; }

.bp3-tree-node-content-14{
  padding-left:322px; }

.bp3-tree-node-content-15{
  padding-left:345px; }

.bp3-tree-node-content-16{
  padding-left:368px; }

.bp3-tree-node-content-17{
  padding-left:391px; }

.bp3-tree-node-content-18{
  padding-left:414px; }

.bp3-tree-node-content-19{
  padding-left:437px; }

.bp3-tree-node-content-20{
  padding-left:460px; }

.bp3-tree-node-content{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  width:100%;
  height:30px;
  padding-right:5px; }
  .bp3-tree-node-content:hover{
    background-color:rgba(191, 204, 214, 0.4); }

.bp3-tree-node-caret,
.bp3-tree-node-caret-none{
  min-width:30px; }

.bp3-tree-node-caret{
  color:#5c7080;
  -webkit-transform:rotate(0deg);
          transform:rotate(0deg);
  cursor:pointer;
  padding:7px;
  -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-tree-node-caret:hover{
    color:#182026; }
  .bp3-dark .bp3-tree-node-caret{
    color:#a7b6c2; }
    .bp3-dark .bp3-tree-node-caret:hover{
      color:#f5f8fa; }
  .bp3-tree-node-caret.bp3-tree-node-caret-open{
    -webkit-transform:rotate(90deg);
            transform:rotate(90deg); }
  .bp3-tree-node-caret.bp3-icon-standard::before{
    content:""; }

.bp3-tree-node-icon{
  position:relative;
  margin-right:7px; }

.bp3-tree-node-label{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  position:relative;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-tree-node-label span{
    display:inline; }

.bp3-tree-node-secondary-label{
  padding:0 5px;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-tree-node-secondary-label .bp3-popover-wrapper,
  .bp3-tree-node-secondary-label .bp3-popover-target{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center; }

.bp3-tree-node.bp3-disabled .bp3-tree-node-content{
  background-color:inherit;
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-tree-node.bp3-disabled .bp3-tree-node-caret,
.bp3-tree-node.bp3-disabled .bp3-tree-node-icon{
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content{
  background-color:#137cbd; }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content,
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon, .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon-standard, .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon-large{
    color:#ffffff; }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-tree-node-caret::before{
    color:rgba(255, 255, 255, 0.7); }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-tree-node-caret:hover::before{
    color:#ffffff; }

.bp3-dark .bp3-tree-node-content:hover{
  background-color:rgba(92, 112, 128, 0.3); }

.bp3-dark .bp3-tree .bp3-icon, .bp3-dark .bp3-tree .bp3-icon-standard, .bp3-dark .bp3-tree .bp3-icon-large{
  color:#a7b6c2; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-primary, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-primary, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-primary{
    color:#137cbd; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-success, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-success, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-success{
    color:#0f9960; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-warning, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-warning, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-warning{
    color:#d9822b; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-danger, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-danger, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-danger{
    color:#db3737; }

.bp3-dark .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content{
  background-color:#137cbd; }
/*!

Copyright 2017-present Palantir Technologies, Inc. All rights reserved.
Licensed under the Apache License, Version 2.0.

*/
.bp3-omnibar{
  -webkit-filter:blur(0);
          filter:blur(0);
  opacity:1;
  top:20vh;
  left:calc(50% - 250px);
  z-index:21;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  background-color:#ffffff;
  width:500px; }
  .bp3-omnibar.bp3-overlay-enter, .bp3-omnibar.bp3-overlay-appear{
    -webkit-filter:blur(20px);
            filter:blur(20px);
    opacity:0.2; }
  .bp3-omnibar.bp3-overlay-enter-active, .bp3-omnibar.bp3-overlay-appear-active{
    -webkit-filter:blur(0);
            filter:blur(0);
    opacity:1;
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:filter, opacity;
    transition-property:filter, opacity, -webkit-filter;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-omnibar.bp3-overlay-exit{
    -webkit-filter:blur(0);
            filter:blur(0);
    opacity:1; }
  .bp3-omnibar.bp3-overlay-exit-active{
    -webkit-filter:blur(20px);
            filter:blur(20px);
    opacity:0.2;
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:filter, opacity;
    transition-property:filter, opacity, -webkit-filter;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-omnibar .bp3-input{
    border-radius:0;
    background-color:transparent; }
    .bp3-omnibar .bp3-input, .bp3-omnibar .bp3-input:focus{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-omnibar .bp3-menu{
    border-radius:0;
    -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
    background-color:transparent;
    max-height:calc(60vh - 40px);
    overflow:auto; }
    .bp3-omnibar .bp3-menu:empty{
      display:none; }
  .bp3-dark .bp3-omnibar, .bp3-omnibar.bp3-dark{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    background-color:#30404d; }

.bp3-omnibar-overlay .bp3-overlay-backdrop{
  background-color:rgba(16, 22, 26, 0.2); }

.bp3-select-popover .bp3-popover-content{
  padding:5px; }

.bp3-select-popover .bp3-input-group{
  margin-bottom:0; }

.bp3-select-popover .bp3-menu{
  max-width:400px;
  max-height:300px;
  overflow:auto;
  padding:0; }
  .bp3-select-popover .bp3-menu:not(:first-child){
    padding-top:5px; }

.bp3-multi-select{
  min-width:150px; }

.bp3-multi-select-popover .bp3-menu{
  max-width:400px;
  max-height:300px;
  overflow:auto; }

.bp3-select-popover .bp3-popover-content{
  padding:5px; }

.bp3-select-popover .bp3-input-group{
  margin-bottom:0; }

.bp3-select-popover .bp3-menu{
  max-width:400px;
  max-height:300px;
  overflow:auto;
  padding:0; }
  .bp3-select-popover .bp3-menu:not(:first-child){
    padding-top:5px; }
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensureUiComponents() in @jupyterlab/buildutils */

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

/* Icons urls */

:root {
  --jp-icon-add: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDEzaC02djZoLTJ2LTZINXYtMmg2VjVoMnY2aDZ2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-bug: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwIDhoLTIuODFjLS40NS0uNzgtMS4wNy0xLjQ1LTEuODItMS45NkwxNyA0LjQxIDE1LjU5IDNsLTIuMTcgMi4xN0MxMi45NiA1LjA2IDEyLjQ5IDUgMTIgNWMtLjQ5IDAtLjk2LjA2LTEuNDEuMTdMOC40MSAzIDcgNC40MWwxLjYyIDEuNjNDNy44OCA2LjU1IDcuMjYgNy4yMiA2LjgxIDhINHYyaDIuMDljLS4wNS4zMy0uMDkuNjYtLjA5IDF2MUg0djJoMnYxYzAgLjM0LjA0LjY3LjA5IDFINHYyaDIuODFjMS4wNCAxLjc5IDIuOTcgMyA1LjE5IDNzNC4xNS0xLjIxIDUuMTktM0gyMHYtMmgtMi4wOWMuMDUtLjMzLjA5LS42Ni4wOS0xdi0xaDJ2LTJoLTJ2LTFjMC0uMzQtLjA0LS42Ny0uMDktMUgyMFY4em0tNiA4aC00di0yaDR2MnptMC00aC00di0yaDR2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-build: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE0LjkgMTcuNDVDMTYuMjUgMTcuNDUgMTcuMzUgMTYuMzUgMTcuMzUgMTVDMTcuMzUgMTMuNjUgMTYuMjUgMTIuNTUgMTQuOSAxMi41NUMxMy41NCAxMi41NSAxMi40NSAxMy42NSAxMi40NSAxNUMxMi40NSAxNi4zNSAxMy41NCAxNy40NSAxNC45IDE3LjQ1Wk0yMC4xIDE1LjY4TDIxLjU4IDE2Ljg0QzIxLjcxIDE2Ljk1IDIxLjc1IDE3LjEzIDIxLjY2IDE3LjI5TDIwLjI2IDE5LjcxQzIwLjE3IDE5Ljg2IDIwIDE5LjkyIDE5LjgzIDE5Ljg2TDE4LjA5IDE5LjE2QzE3LjczIDE5LjQ0IDE3LjMzIDE5LjY3IDE2LjkxIDE5Ljg1TDE2LjY0IDIxLjdDMTYuNjIgMjEuODcgMTYuNDcgMjIgMTYuMyAyMkgxMy41QzEzLjMyIDIyIDEzLjE4IDIxLjg3IDEzLjE1IDIxLjdMMTIuODkgMTkuODVDMTIuNDYgMTkuNjcgMTIuMDcgMTkuNDQgMTEuNzEgMTkuMTZMOS45NjAwMiAxOS44NkM5LjgxMDAyIDE5LjkyIDkuNjIwMDIgMTkuODYgOS41NDAwMiAxOS43MUw4LjE0MDAyIDE3LjI5QzguMDUwMDIgMTcuMTMgOC4wOTAwMiAxNi45NSA4LjIyMDAyIDE2Ljg0TDkuNzAwMDIgMTUuNjhMOS42NTAwMSAxNUw5LjcwMDAyIDE0LjMxTDguMjIwMDIgMTMuMTZDOC4wOTAwMiAxMy4wNSA4LjA1MDAyIDEyLjg2IDguMTQwMDIgMTIuNzFMOS41NDAwMiAxMC4yOUM5LjYyMDAyIDEwLjEzIDkuODEwMDIgMTAuMDcgOS45NjAwMiAxMC4xM0wxMS43MSAxMC44NEMxMi4wNyAxMC41NiAxMi40NiAxMC4zMiAxMi44OSAxMC4xNUwxMy4xNSA4LjI4OTk4QzEzLjE4IDguMTI5OTggMTMuMzIgNy45OTk5OCAxMy41IDcuOTk5OThIMTYuM0MxNi40NyA3Ljk5OTk4IDE2LjYyIDguMTI5OTggMTYuNjQgOC4yODk5OEwxNi45MSAxMC4xNUMxNy4zMyAxMC4zMiAxNy43MyAxMC41NiAxOC4wOSAxMC44NEwxOS44MyAxMC4xM0MyMCAxMC4wNyAyMC4xNyAxMC4xMyAyMC4yNiAxMC4yOUwyMS42NiAxMi43MUMyMS43NSAxMi44NiAyMS43MSAxMy4wNSAyMS41OCAxMy4xNkwyMC4xIDE0LjMxTDIwLjE1IDE1TDIwLjEgMTUuNjhaIi8+CiAgICA8cGF0aCBkPSJNNy4zMjk2NiA3LjQ0NDU0QzguMDgzMSA3LjAwOTU0IDguMzM5MzIgNi4wNTMzMiA3LjkwNDMyIDUuMjk5ODhDNy40NjkzMiA0LjU0NjQzIDYuNTA4MSA0LjI4MTU2IDUuNzU0NjYgNC43MTY1NkM1LjM5MTc2IDQuOTI2MDggNS4xMjY5NSA1LjI3MTE4IDUuMDE4NDkgNS42NzU5NEM0LjkxMDA0IDYuMDgwNzEgNC45NjY4MiA2LjUxMTk4IDUuMTc2MzQgNi44NzQ4OEM1LjYxMTM0IDcuNjI4MzIgNi41NzYyMiA3Ljg3OTU0IDcuMzI5NjYgNy40NDQ1NFpNOS42NTcxOCA0Ljc5NTkzTDEwLjg2NzIgNC45NTE3OUMxMC45NjI4IDQuOTc3NDEgMTEuMDQwMiA1LjA3MTMzIDExLjAzODIgNS4xODc5M0wxMS4wMzg4IDYuOTg4OTNDMTEuMDQ1NSA3LjEwMDU0IDEwLjk2MTYgNy4xOTUxOCAxMC44NTUgNy4yMTA1NEw5LjY2MDAxIDcuMzgwODNMOS4yMzkxNSA4LjEzMTg4TDkuNjY5NjEgOS4yNTc0NUM5LjcwNzI5IDkuMzYyNzEgOS42NjkzNCA5LjQ3Njk5IDkuNTc0MDggOS41MzE5OUw4LjAxNTIzIDEwLjQzMkM3LjkxMTMxIDEwLjQ5MiA3Ljc5MzM3IDEwLjQ2NzcgNy43MjEwNSAxMC4zODI0TDYuOTg3NDggOS40MzE4OEw2LjEwOTMxIDkuNDMwODNMNS4zNDcwNCAxMC4zOTA1QzUuMjg5MDkgMTAuNDcwMiA1LjE3MzgzIDEwLjQ5MDUgNS4wNzE4NyAxMC40MzM5TDMuNTEyNDUgOS41MzI5M0MzLjQxMDQ5IDkuNDc2MzMgMy4zNzY0NyA5LjM1NzQxIDMuNDEwNzUgOS4yNTY3OUwzLjg2MzQ3IDguMTQwOTNMMy42MTc0OSA3Ljc3NDg4TDMuNDIzNDcgNy4zNzg4M0wyLjIzMDc1IDcuMjEyOTdDMi4xMjY0NyA3LjE5MjM1IDIuMDQwNDkgNy4xMDM0MiAyLjA0MjQ1IDYuOTg2ODJMMi4wNDE4NyA1LjE4NTgyQzIuMDQzODMgNS4wNjkyMiAyLjExOTA5IDQuOTc5NTggMi4yMTcwNCA0Ljk2OTIyTDMuNDIwNjUgNC43OTM5M0wzLjg2NzQ5IDQuMDI3ODhMMy40MTEwNSAyLjkxNzMxQzMuMzczMzcgMi44MTIwNCAzLjQxMTMxIDIuNjk3NzYgMy41MTUyMyAyLjYzNzc2TDUuMDc0MDggMS43Mzc3NkM1LjE2OTM0IDEuNjgyNzYgNS4yODcyOSAxLjcwNzA0IDUuMzU5NjEgMS43OTIzMUw2LjExOTE1IDIuNzI3ODhMNi45ODAwMSAyLjczODkzTDcuNzI0OTYgMS43ODkyMkM3Ljc5MTU2IDEuNzA0NTggNy45MTU0OCAxLjY3OTIyIDguMDA4NzkgMS43NDA4Mkw5LjU2ODIxIDIuNjQxODJDOS42NzAxNyAyLjY5ODQyIDkuNzEyODUgMi44MTIzNCA5LjY4NzIzIDIuOTA3OTdMOS4yMTcxOCA0LjAzMzgzTDkuNDYzMTYgNC4zOTk4OEw5LjY1NzE4IDQuNzk1OTNaIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iOS45LDEzLjYgMy42LDcuNCA0LjQsNi42IDkuOSwxMi4yIDE1LjQsNi43IDE2LjEsNy40ICIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNS45TDksOS43bDMuOC0zLjhsMS4yLDEuMmwtNC45LDVsLTQuOS01TDUuMiw1Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNy41TDksMTEuMmwzLjgtMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-left: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik0xMC44LDEyLjhMNy4xLDlsMy44LTMuOGwwLDcuNkgxMC44eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-right: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik03LjIsNS4yTDEwLjksOWwtMy44LDMuOFY1LjJINy4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-up-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iMTUuNCwxMy4zIDkuOSw3LjcgNC40LDEzLjIgMy42LDEyLjUgOS45LDYuMyAxNi4xLDEyLjYgIi8+Cgk8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-up: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik01LjIsMTAuNUw5LDYuOGwzLjgsMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-case-sensitive: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgogIDxnIGNsYXNzPSJqcC1pY29uLWFjY2VudDIiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTcuNiw4aDAuOWwzLjUsOGgtMS4xTDEwLDE0SDZsLTAuOSwySDRMNy42LDh6IE04LDkuMUw2LjQsMTNoMy4yTDgsOS4xeiIvPgogICAgPHBhdGggZD0iTTE2LjYsOS44Yy0wLjIsMC4xLTAuNCwwLjEtMC43LDAuMWMtMC4yLDAtMC40LTAuMS0wLjYtMC4yYy0wLjEtMC4xLTAuMi0wLjQtMC4yLTAuNyBjLTAuMywwLjMtMC42LDAuNS0wLjksMC43Yy0wLjMsMC4xLTAuNywwLjItMS4xLDAuMmMtMC4zLDAtMC41LDAtMC43LTAuMWMtMC4yLTAuMS0wLjQtMC4yLTAuNi0wLjNjLTAuMi0wLjEtMC4zLTAuMy0wLjQtMC41IGMtMC4xLTAuMi0wLjEtMC40LTAuMS0wLjdjMC0wLjMsMC4xLTAuNiwwLjItMC44YzAuMS0wLjIsMC4zLTAuNCwwLjQtMC41QzEyLDcsMTIuMiw2LjksMTIuNSw2LjhjMC4yLTAuMSwwLjUtMC4xLDAuNy0wLjIgYzAuMy0wLjEsMC41LTAuMSwwLjctMC4xYzAuMiwwLDAuNC0wLjEsMC42LTAuMWMwLjIsMCwwLjMtMC4xLDAuNC0wLjJjMC4xLTAuMSwwLjItMC4yLDAuMi0wLjRjMC0xLTEuMS0xLTEuMy0xIGMtMC40LDAtMS40LDAtMS40LDEuMmgtMC45YzAtMC40LDAuMS0wLjcsMC4yLTFjMC4xLTAuMiwwLjMtMC40LDAuNS0wLjZjMC4yLTAuMiwwLjUtMC4zLDAuOC0wLjNDMTMuMyw0LDEzLjYsNCwxMy45LDQgYzAuMywwLDAuNSwwLDAuOCwwLjFjMC4zLDAsMC41LDAuMSwwLjcsMC4yYzAuMiwwLjEsMC40LDAuMywwLjUsMC41QzE2LDUsMTYsNS4yLDE2LDUuNnYyLjljMCwwLjIsMCwwLjQsMCwwLjUgYzAsMC4xLDAuMSwwLjIsMC4zLDAuMmMwLjEsMCwwLjIsMCwwLjMsMFY5Ljh6IE0xNS4yLDYuOWMtMS4yLDAuNi0zLjEsMC4yLTMuMSwxLjRjMCwxLjQsMy4xLDEsMy4xLTAuNVY2Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-check: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkgMTYuMTdMNC44MyAxMmwtMS40MiAxLjQxTDkgMTkgMjEgN2wtMS40MS0xLjQxeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-circle-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyIDJDNi40NyAyIDIgNi40NyAyIDEyczQuNDcgMTAgMTAgMTAgMTAtNC40NyAxMC0xMFMxNy41MyAyIDEyIDJ6bTAgMThjLTQuNDEgMC04LTMuNTktOC04czMuNTktOCA4LTggOCAzLjU5IDggOC0zLjU5IDgtOCA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-circle: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iOSIgY3k9IjkiIHI9IjgiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-clear: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8bWFzayBpZD0iZG9udXRIb2xlIj4KICAgIDxyZWN0IHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgZmlsbD0id2hpdGUiIC8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSI4IiBmaWxsPSJibGFjayIvPgogIDwvbWFzaz4KCiAgPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxyZWN0IGhlaWdodD0iMTgiIHdpZHRoPSIyIiB4PSIxMSIgeT0iMyIgdHJhbnNmb3JtPSJyb3RhdGUoMzE1LCAxMiwgMTIpIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIxMCIgbWFzaz0idXJsKCNkb251dEhvbGUpIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-close: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1ub25lIGpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIGpwLWljb24zLWhvdmVyIiBmaWxsPSJub25lIj4KICAgIDxjaXJjbGUgY3g9IjEyIiBjeT0iMTIiIHI9IjExIi8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIGpwLWljb24tYWNjZW50Mi1ob3ZlciIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMTkgNi40MUwxNy41OSA1IDEyIDEwLjU5IDYuNDEgNSA1IDYuNDEgMTAuNTkgMTIgNSAxNy41OSA2LjQxIDE5IDEyIDEzLjQxIDE3LjU5IDE5IDE5IDE3LjU5IDEzLjQxIDEyeiIvPgogIDwvZz4KCiAgPGcgY2xhc3M9ImpwLWljb24tbm9uZSBqcC1pY29uLWJ1c3kiIGZpbGw9Im5vbmUiPgogICAgPGNpcmNsZSBjeD0iMTIiIGN5PSIxMiIgcj0iNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-console: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwMCAyMDAiPgogIDxnIGNsYXNzPSJqcC1pY29uLWJyYW5kMSBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMjg4RDEiPgogICAgPHBhdGggZD0iTTIwIDE5LjhoMTYwdjE1OS45SDIweiIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNmZmYiPgogICAgPHBhdGggZD0iTTEwNSAxMjcuM2g0MHYxMi44aC00MHpNNTEuMSA3N0w3NCA5OS45bC0yMy4zIDIzLjMgMTAuNSAxMC41IDIzLjMtMjMuM0w5NSA5OS45IDg0LjUgODkuNCA2MS42IDY2LjV6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-copy: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTExLjksMUgzLjJDMi40LDEsMS43LDEuNywxLjcsMi41djEwLjJoMS41VjIuNWg4LjdWMXogTTE0LjEsMy45aC04Yy0wLjgsMC0xLjUsMC43LTEuNSwxLjV2MTAuMmMwLDAuOCwwLjcsMS41LDEuNSwxLjVoOCBjMC44LDAsMS41LTAuNywxLjUtMS41VjUuNEMxNS41LDQuNiwxNC45LDMuOSwxNC4xLDMuOXogTTE0LjEsMTUuNWgtOFY1LjRoOFYxNS41eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-cut: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkuNjQgNy42NGMuMjMtLjUuMzYtMS4wNS4zNi0xLjY0IDAtMi4yMS0xLjc5LTQtNC00UzIgMy43OSAyIDZzMS43OSA0IDQgNGMuNTkgMCAxLjE0LS4xMyAxLjY0LS4zNkwxMCAxMmwtMi4zNiAyLjM2QzcuMTQgMTQuMTMgNi41OSAxNCA2IDE0Yy0yLjIxIDAtNCAxLjc5LTQgNHMxLjc5IDQgNCA0IDQtMS43OSA0LTRjMC0uNTktLjEzLTEuMTQtLjM2LTEuNjRMMTIgMTRsNyA3aDN2LTFMOS42NCA3LjY0ek02IDhjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTAgMTJjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTYtNy41Yy0uMjggMC0uNS0uMjItLjUtLjVzLjIyLS41LjUtLjUuNS4yMi41LjUtLjIyLjUtLjUuNXpNMTkgM2wtNiA2IDIgMiA3LTdWM3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-download: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDloLTRWM0g5djZINWw3IDcgNy03ek01IDE4djJoMTR2LTJINXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-edit: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMgMTcuMjVWMjFoMy43NUwxNy44MSA5Ljk0bC0zLjc1LTMuNzVMMyAxNy4yNXpNMjAuNzEgNy4wNGMuMzktLjM5LjM5LTEuMDIgMC0xLjQxbC0yLjM0LTIuMzRjLS4zOS0uMzktMS4wMi0uMzktMS40MSAwbC0xLjgzIDEuODMgMy43NSAzLjc1IDEuODMtMS44M3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-ellipses: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iNSIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxOSIgY3k9IjEyIiByPSIyIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-extension: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwLjUgMTFIMTlWN2MwLTEuMS0uOS0yLTItMmgtNFYzLjVDMTMgMi4xMiAxMS44OCAxIDEwLjUgMVM4IDIuMTIgOCAzLjVWNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAydjMuOEgzLjVjMS40OSAwIDIuNyAxLjIxIDIuNyAyLjdzLTEuMjEgMi43LTIuNyAyLjdIMlYyMGMwIDEuMS45IDIgMiAyaDMuOHYtMS41YzAtMS40OSAxLjIxLTIuNyAyLjctMi43IDEuNDkgMCAyLjcgMS4yMSAyLjcgMi43VjIySDE3YzEuMSAwIDItLjkgMi0ydi00aDEuNWMxLjM4IDAgMi41LTEuMTIgMi41LTIuNVMyMS44OCAxMSAyMC41IDExeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-fast-forward: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTQgMThsOC41LTZMNCA2djEyem05LTEydjEybDguNS02TDEzIDZ6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-file-upload: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkgMTZoNnYtNmg0bC03LTctNyA3aDR6bS00IDJoMTR2Mkg1eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-file: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuMyA4LjJsLTUuNS01LjVjLS4zLS4zLS43LS41LTEuMi0uNUgzLjljLS44LjEtMS42LjktMS42IDEuOHYxNC4xYzAgLjkuNyAxLjYgMS42IDEuNmgxNC4yYy45IDAgMS42LS43IDEuNi0xLjZWOS40Yy4xLS41LS4xLS45LS40LTEuMnptLTUuOC0zLjNsMy40IDMuNmgtMy40VjQuOXptMy45IDEyLjdINC43Yy0uMSAwLS4yIDAtLjItLjJWNC43YzAtLjIuMS0uMy4yLS4zaDcuMnY0LjRzMCAuOC4zIDEuMWMuMy4zIDEuMS4zIDEuMS4zaDQuM3Y3LjJzLS4xLjItLjIuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-filter-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEwIDE4aDR2LTJoLTR2MnpNMyA2djJoMThWNkgzem0zIDdoMTJ2LTJINnYyeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY4YzAtMS4xLS45LTItMi0yaC04bC0yLTJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-html5: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uMCBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMDAiIGQ9Ik0xMDguNCAwaDIzdjIyLjhoMjEuMlYwaDIzdjY5aC0yM1Y0NmgtMjF2MjNoLTIzLjJNMjA2IDIzaC0yMC4zVjBoNjMuN3YyM0gyMjl2NDZoLTIzbTUzLjUtNjloMjQuMWwxNC44IDI0LjNMMzEzLjIgMGgyNC4xdjY5aC0yM1YzNC44bC0xNi4xIDI0LjgtMTYuMS0yNC44VjY5aC0yMi42bTg5LjItNjloMjN2NDYuMmgzMi42VjY5aC01NS42Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI2U0NGQyNiIgZD0iTTEwNy42IDQ3MWwtMzMtMzcwLjRoMzYyLjhsLTMzIDM3MC4yTDI1NS43IDUxMiIvPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNmMTY1MjkiIGQ9Ik0yNTYgNDgwLjVWMTMxaDE0OC4zTDM3NiA0NDciLz4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNlYmViZWIiIGQ9Ik0xNDIgMTc2LjNoMTE0djQ1LjRoLTY0LjJsNC4yIDQ2LjVoNjB2NDUuM0gxNTQuNG0yIDIyLjhIMjAybDMuMiAzNi4zIDUwLjggMTMuNnY0Ny40bC05My4yLTI2Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIiBmaWxsPSIjZmZmIiBkPSJNMzY5LjYgMTc2LjNIMjU1Ljh2NDUuNGgxMDkuNm0tNC4xIDQ2LjVIMjU1Ljh2NDUuNGg1NmwtNS4zIDU5LTUwLjcgMTMuNnY0Ny4ybDkzLTI1LjgiLz4KPC9zdmc+Cg==);
  --jp-icon-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1icmFuZDQganAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNGRkYiIGQ9Ik0yLjIgMi4yaDE3LjV2MTcuNUgyLjJ6Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzNGNTFCNSIgZD0iTTIuMiAyLjJ2MTcuNWgxNy41bC4xLTE3LjVIMi4yem0xMi4xIDIuMmMxLjIgMCAyLjIgMSAyLjIgMi4ycy0xIDIuMi0yLjIgMi4yLTIuMi0xLTIuMi0yLjIgMS0yLjIgMi4yLTIuMnpNNC40IDE3LjZsMy4zLTguOCAzLjMgNi42IDIuMi0zLjIgNC40IDUuNEg0LjR6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-inspector: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY2YzAtMS4xLS45LTItMi0yem0tNSAxNEg0di00aDExdjR6bTAtNUg0VjloMTF2NHptNSA1aC00VjloNHY5eiIvPgo8L3N2Zz4K);
  --jp-icon-json: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMSBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNGOUE4MjUiPgogICAgPHBhdGggZD0iTTIwLjIgMTEuOGMtMS42IDAtMS43LjUtMS43IDEgMCAuNC4xLjkuMSAxLjMuMS41LjEuOS4xIDEuMyAwIDEuNy0xLjQgMi4zLTMuNSAyLjNoLS45di0xLjloLjVjMS4xIDAgMS40IDAgMS40LS44IDAtLjMgMC0uNi0uMS0xIDAtLjQtLjEtLjgtLjEtMS4yIDAtMS4zIDAtMS44IDEuMy0yLTEuMy0uMi0xLjMtLjctMS4zLTIgMC0uNC4xLS44LjEtMS4yLjEtLjQuMS0uNy4xLTEgMC0uOC0uNC0uNy0xLjQtLjhoLS41VjQuMWguOWMyLjIgMCAzLjUuNyAzLjUgMi4zIDAgLjQtLjEuOS0uMSAxLjMtLjEuNS0uMS45LS4xIDEuMyAwIC41LjIgMSAxLjcgMXYxLjh6TTEuOCAxMC4xYzEuNiAwIDEuNy0uNSAxLjctMSAwLS40LS4xLS45LS4xLTEuMy0uMS0uNS0uMS0uOS0uMS0xLjMgMC0xLjYgMS40LTIuMyAzLjUtMi4zaC45djEuOWgtLjVjLTEgMC0xLjQgMC0xLjQuOCAwIC4zIDAgLjYuMSAxIDAgLjIuMS42LjEgMSAwIDEuMyAwIDEuOC0xLjMgMkM2IDExLjIgNiAxMS43IDYgMTNjMCAuNC0uMS44LS4xIDEuMi0uMS4zLS4xLjctLjEgMSAwIC44LjMuOCAxLjQuOGguNXYxLjloLS45Yy0yLjEgMC0zLjUtLjYtMy41LTIuMyAwLS40LjEtLjkuMS0xLjMuMS0uNS4xLS45LjEtMS4zIDAtLjUtLjItMS0xLjctMXYtMS45eiIvPgogICAgPGNpcmNsZSBjeD0iMTEiIGN5PSIxMy44IiByPSIyLjEiLz4KICAgIDxjaXJjbGUgY3g9IjExIiBjeT0iOC4yIiByPSIyLjEiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-jupyter-favicon: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTUyIiBoZWlnaHQ9IjE2NSIgdmlld0JveD0iMCAwIDE1MiAxNjUiIHZlcnNpb249IjEuMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA3ODk0NywgMTEwLjU4MjkyNykiIGQ9Ik03NS45NDIyODQyLDI5LjU4MDQ1NjEgQzQzLjMwMjM5NDcsMjkuNTgwNDU2MSAxNC43OTY3ODMyLDE3LjY1MzQ2MzQgMCwwIEM1LjUxMDgzMjExLDE1Ljg0MDY4MjkgMTUuNzgxNTM4OSwyOS41NjY3NzMyIDI5LjM5MDQ5NDcsMzkuMjc4NDE3MSBDNDIuOTk5Nyw0OC45ODk4NTM3IDU5LjI3MzcsNTQuMjA2NzgwNSA3NS45NjA1Nzg5LDU0LjIwNjc4MDUgQzkyLjY0NzQ1NzksNTQuMjA2NzgwNSAxMDguOTIxNDU4LDQ4Ljk4OTg1MzcgMTIyLjUzMDY2MywzOS4yNzg0MTcxIEMxMzYuMTM5NDUzLDI5LjU2Njc3MzIgMTQ2LjQxMDI4NCwxNS44NDA2ODI5IDE1MS45MjExNTgsMCBDMTM3LjA4Nzg2OCwxNy42NTM0NjM0IDEwOC41ODI1ODksMjkuNTgwNDU2MSA3NS45NDIyODQyLDI5LjU4MDQ1NjEgTDc1Ljk0MjI4NDIsMjkuNTgwNDU2MSBaIiAvPgogICAgPHBhdGggdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMzczNjgsIDAuNzA0ODc4KSIgZD0iTTc1Ljk3ODQ1NzksMjQuNjI2NDA3MyBDMTA4LjYxODc2MywyNC42MjY0MDczIDEzNy4xMjQ0NTgsMzYuNTUzNDQxNSAxNTEuOTIxMTU4LDU0LjIwNjc4MDUgQzE0Ni40MTAyODQsMzguMzY2MjIyIDEzNi4xMzk0NTMsMjQuNjQwMTMxNyAxMjIuNTMwNjYzLDE0LjkyODQ4NzggQzEwOC45MjE0NTgsNS4yMTY4NDM5IDkyLjY0NzQ1NzksMCA3NS45NjA1Nzg5LDAgQzU5LjI3MzcsMCA0Mi45OTk3LDUuMjE2ODQzOSAyOS4zOTA0OTQ3LDE0LjkyODQ4NzggQzE1Ljc4MTUzODksMjQuNjQwMTMxNyA1LjUxMDgzMjExLDM4LjM2NjIyMiAwLDU0LjIwNjc4MDUgQzE0LjgzMzA4MTYsMzYuNTg5OTI5MyA0My4zMzg1Njg0LDI0LjYyNjQwNzMgNzUuOTc4NDU3OSwyNC42MjY0MDczIEw3NS45Nzg0NTc5LDI0LjYyNjQwNzMgWiIgLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-jupyter: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzkiIGhlaWdodD0iNTEiIHZpZXdCb3g9IjAgMCAzOSA1MSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgtMTYzOCAtMjI4MSkiPgogICAgPGcgY2xhc3M9ImpwLWljb24td2FybjAiIGZpbGw9IiNGMzc3MjYiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5Ljc0IDIzMTEuOTgpIiBkPSJNIDE4LjI2NDYgNy4xMzQxMUMgMTAuNDE0NSA3LjEzNDExIDMuNTU4NzIgNC4yNTc2IDAgMEMgMS4zMjUzOSAzLjgyMDQgMy43OTU1NiA3LjEzMDgxIDcuMDY4NiA5LjQ3MzAzQyAxMC4zNDE3IDExLjgxNTIgMTQuMjU1NyAxMy4wNzM0IDE4LjI2OSAxMy4wNzM0QyAyMi4yODIzIDEzLjA3MzQgMjYuMTk2MyAxMS44MTUyIDI5LjQ2OTQgOS40NzMwM0MgMzIuNzQyNCA3LjEzMDgxIDM1LjIxMjYgMy44MjA0IDM2LjUzOCAwQyAzMi45NzA1IDQuMjU3NiAyNi4xMTQ4IDcuMTM0MTEgMTguMjY0NiA3LjEzNDExWiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5LjczIDIyODUuNDgpIiBkPSJNIDE4LjI3MzMgNS45MzkzMUMgMjYuMTIzNSA1LjkzOTMxIDMyLjk3OTMgOC44MTU4MyAzNi41MzggMTMuMDczNEMgMzUuMjEyNiA5LjI1MzAzIDMyLjc0MjQgNS45NDI2MiAyOS40Njk0IDMuNjAwNEMgMjYuMTk2MyAxLjI1ODE4IDIyLjI4MjMgMCAxOC4yNjkgMEMgMTQuMjU1NyAwIDEwLjM0MTcgMS4yNTgxOCA3LjA2ODYgMy42MDA0QyAzLjc5NTU2IDUuOTQyNjIgMS4zMjUzOSA5LjI1MzAzIDAgMTMuMDczNEMgMy41Njc0NSA4LjgyNDYzIDEwLjQyMzIgNS45MzkzMSAxOC4yNzMzIDUuOTM5MzFaIi8+CiAgICA8L2c+CiAgICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjY5LjMgMjI4MS4zMSkiIGQ9Ik0gNS44OTM1MyAyLjg0NEMgNS45MTg4OSAzLjQzMTY1IDUuNzcwODUgNC4wMTM2NyA1LjQ2ODE1IDQuNTE2NDVDIDUuMTY1NDUgNS4wMTkyMiA0LjcyMTY4IDUuNDIwMTUgNC4xOTI5OSA1LjY2ODUxQyAzLjY2NDMgNS45MTY4OCAzLjA3NDQ0IDYuMDAxNTEgMi40OTgwNSA1LjkxMTcxQyAxLjkyMTY2IDUuODIxOSAxLjM4NDYzIDUuNTYxNyAwLjk1NDg5OCA1LjE2NDAxQyAwLjUyNTE3IDQuNzY2MzMgMC4yMjIwNTYgNC4yNDkwMyAwLjA4MzkwMzcgMy42Nzc1N0MgLTAuMDU0MjQ4MyAzLjEwNjExIC0wLjAyMTIzIDIuNTA2MTcgMC4xNzg3ODEgMS45NTM2NEMgMC4zNzg3OTMgMS40MDExIDAuNzM2ODA5IDAuOTIwODE3IDEuMjA3NTQgMC41NzM1MzhDIDEuNjc4MjYgMC4yMjYyNTkgMi4yNDA1NSAwLjAyNzU5MTkgMi44MjMyNiAwLjAwMjY3MjI5QyAzLjYwMzg5IC0wLjAzMDcxMTUgNC4zNjU3MyAwLjI0OTc4OSA0Ljk0MTQyIDAuNzgyNTUxQyA1LjUxNzExIDEuMzE1MzEgNS44NTk1NiAyLjA1Njc2IDUuODkzNTMgMi44NDRaIi8+CiAgICAgIDxwYXRoIHRyYW5zZm9ybT0idHJhbnNsYXRlKDE2MzkuOCAyMzIzLjgxKSIgZD0iTSA3LjQyNzg5IDMuNTgzMzhDIDcuNDYwMDggNC4zMjQzIDcuMjczNTUgNS4wNTgxOSA2Ljg5MTkzIDUuNjkyMTNDIDYuNTEwMzEgNi4zMjYwNyA1Ljk1MDc1IDYuODMxNTYgNS4yODQxMSA3LjE0NDZDIDQuNjE3NDcgNy40NTc2MyAzLjg3MzcxIDcuNTY0MTQgMy4xNDcwMiA3LjQ1MDYzQyAyLjQyMDMyIDcuMzM3MTIgMS43NDMzNiA3LjAwODcgMS4yMDE4NCA2LjUwNjk1QyAwLjY2MDMyOCA2LjAwNTIgMC4yNzg2MSA1LjM1MjY4IDAuMTA1MDE3IDQuNjMyMDJDIC0wLjA2ODU3NTcgMy45MTEzNSAtMC4wMjYyMzYxIDMuMTU0OTQgMC4yMjY2NzUgMi40NTg1NkMgMC40Nzk1ODcgMS43NjIxNyAwLjkzMTY5NyAxLjE1NzEzIDEuNTI1NzYgMC43MjAwMzNDIDIuMTE5ODMgMC4yODI5MzUgMi44MjkxNCAwLjAzMzQzOTUgMy41NjM4OSAwLjAwMzEzMzQ0QyA0LjU0NjY3IC0wLjAzNzQwMzMgNS41MDUyOSAwLjMxNjcwNiA2LjIyOTYxIDAuOTg3ODM1QyA2Ljk1MzkzIDEuNjU4OTYgNy4zODQ4NCAyLjU5MjM1IDcuNDI3ODkgMy41ODMzOEwgNy40Mjc4OSAzLjU4MzM4WiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM4LjM2IDIyODYuMDYpIiBkPSJNIDIuMjc0NzEgNC4zOTYyOUMgMS44NDM2MyA0LjQxNTA4IDEuNDE2NzEgNC4zMDQ0NSAxLjA0Nzk5IDQuMDc4NDNDIDAuNjc5MjY4IDMuODUyNCAwLjM4NTMyOCAzLjUyMTE0IDAuMjAzMzcxIDMuMTI2NTZDIDAuMDIxNDEzNiAyLjczMTk4IC0wLjA0MDM3OTggMi4yOTE4MyAwLjAyNTgxMTYgMS44NjE4MUMgMC4wOTIwMDMxIDEuNDMxOCAwLjI4MzIwNCAxLjAzMTI2IDAuNTc1MjEzIDAuNzEwODgzQyAwLjg2NzIyMiAwLjM5MDUxIDEuMjQ2OTEgMC4xNjQ3MDggMS42NjYyMiAwLjA2MjA1OTJDIDIuMDg1NTMgLTAuMDQwNTg5NyAyLjUyNTYxIC0wLjAxNTQ3MTQgMi45MzA3NiAwLjEzNDIzNUMgMy4zMzU5MSAwLjI4Mzk0MSAzLjY4NzkyIDAuNTUxNTA1IDMuOTQyMjIgMC45MDMwNkMgNC4xOTY1MiAxLjI1NDYyIDQuMzQxNjkgMS42NzQzNiA0LjM1OTM1IDIuMTA5MTZDIDQuMzgyOTkgMi42OTEwNyA0LjE3Njc4IDMuMjU4NjkgMy43ODU5NyAzLjY4NzQ2QyAzLjM5NTE2IDQuMTE2MjQgMi44NTE2NiA0LjM3MTE2IDIuMjc0NzEgNC4zOTYyOUwgMi4yNzQ3MSA0LjM5NjI5WiIvPgogICAgPC9nPgogIDwvZz4+Cjwvc3ZnPgo=);
  --jp-icon-jupyterlab-wordmark: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyMDAiIHZpZXdCb3g9IjAgMCAxODYwLjggNDc1Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0RTRFNEUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDQ4MC4xMzY0MDEsIDY0LjI3MTQ5MykiPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMDAwMDAsIDU4Ljg3NTU2NikiPgogICAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA4NzYwMywgMC4xNDAyOTQpIj4KICAgICAgICA8cGF0aCBkPSJNLTQyNi45LDE2OS44YzAsNDguNy0zLjcsNjQuNy0xMy42LDc2LjRjLTEwLjgsMTAtMjUsMTUuNS0zOS43LDE1LjVsMy43LDI5IGMyMi44LDAuMyw0NC44LTcuOSw2MS45LTIzLjFjMTcuOC0xOC41LDI0LTQ0LjEsMjQtODMuM1YwSC00Mjd2MTcwLjFMLTQyNi45LDE2OS44TC00MjYuOSwxNjkuOHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTU1LjA0NTI5NiwgNTYuODM3MTA0KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuNTYyNDUzLCAxLjc5OTg0MikiPgogICAgICAgIDxwYXRoIGQ9Ik0tMzEyLDE0OGMwLDIxLDAsMzkuNSwxLjcsNTUuNGgtMzEuOGwtMi4xLTMzLjNoLTAuOGMtNi43LDExLjYtMTYuNCwyMS4zLTI4LDI3LjkgYy0xMS42LDYuNi0yNC44LDEwLTM4LjIsOS44Yy0zMS40LDAtNjktMTcuNy02OS04OVYwaDM2LjR2MTEyLjdjMCwzOC43LDExLjYsNjQuNyw0NC42LDY0LjdjMTAuMy0wLjIsMjAuNC0zLjUsMjguOS05LjQgYzguNS01LjksMTUuMS0xNC4zLDE4LjktMjMuOWMyLjItNi4xLDMuMy0xMi41LDMuMy0xOC45VjAuMmgzNi40VjE0OEgtMzEyTC0zMTIsMTQ4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzOTAuMDEzMzIyLCA1My40Nzk2MzgpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS43MDY0NTgsIDAuMjMxNDI1KSI+CiAgICAgICAgPHBhdGggZD0iTS00NzguNiw3MS40YzAtMjYtMC44LTQ3LTEuNy02Ni43aDMyLjdsMS43LDM0LjhoMC44YzcuMS0xMi41LDE3LjUtMjIuOCwzMC4xLTI5LjcgYzEyLjUtNywyNi43LTEwLjMsNDEtOS44YzQ4LjMsMCw4NC43LDQxLjcsODQuNywxMDMuM2MwLDczLjEtNDMuNywxMDkuMi05MSwxMDkuMmMtMTIuMSwwLjUtMjQuMi0yLjItMzUtNy44IGMtMTAuOC01LjYtMTkuOS0xMy45LTI2LjYtMjQuMmgtMC44VjI5MWgtMzZ2LTIyMEwtNDc4LjYsNzEuNEwtNDc4LjYsNzEuNHogTS00NDIuNiwxMjUuNmMwLjEsNS4xLDAuNiwxMC4xLDEuNywxNS4xIGMzLDEyLjMsOS45LDIzLjMsMTkuOCwzMS4xYzkuOSw3LjgsMjIuMSwxMi4xLDM0LjcsMTIuMWMzOC41LDAsNjAuNy0zMS45LDYwLjctNzguNWMwLTQwLjctMjEuMS03NS42LTU5LjUtNzUuNiBjLTEyLjksMC40LTI1LjMsNS4xLTM1LjMsMTMuNGMtOS45LDguMy0xNi45LDE5LjctMTkuNiwzMi40Yy0xLjUsNC45LTIuMywxMC0yLjUsMTUuMVYxMjUuNkwtNDQyLjYsMTI1LjZMLTQ0Mi42LDEyNS42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSg2MDYuNzQwNzI2LCA1Ni44MzcxMDQpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC43NTEyMjYsIDEuOTg5Mjk5KSI+CiAgICAgICAgPHBhdGggZD0iTS00NDAuOCwwbDQzLjcsMTIwLjFjNC41LDEzLjQsOS41LDI5LjQsMTIuOCw0MS43aDAuOGMzLjctMTIuMiw3LjktMjcuNywxMi44LTQyLjQgbDM5LjctMTE5LjJoMzguNUwtMzQ2LjksMTQ1Yy0yNiw2OS43LTQzLjcsMTA1LjQtNjguNiwxMjcuMmMtMTIuNSwxMS43LTI3LjksMjAtNDQuNiwyMy45bC05LjEtMzEuMSBjMTEuNy0zLjksMjIuNS0xMC4xLDMxLjgtMTguMWMxMy4yLTExLjEsMjMuNy0yNS4yLDMwLjYtNDEuMmMxLjUtMi44LDIuNS01LjcsMi45LTguOGMtMC4zLTMuMy0xLjItNi42LTIuNS05LjdMLTQ4MC4yLDAuMSBoMzkuN0wtNDQwLjgsMEwtNDQwLjgsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoODIyLjc0ODEwNCwgMC4wMDAwMDApIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS40NjQwNTAsIDAuMzc4OTE0KSI+CiAgICAgICAgPHBhdGggZD0iTS00MTMuNywwdjU4LjNoNTJ2MjguMmgtNTJWMTk2YzAsMjUsNywzOS41LDI3LjMsMzkuNWM3LjEsMC4xLDE0LjItMC43LDIxLjEtMi41IGwxLjcsMjcuN2MtMTAuMywzLjctMjEuMyw1LjQtMzIuMiw1Yy03LjMsMC40LTE0LjYtMC43LTIxLjMtMy40Yy02LjgtMi43LTEyLjktNi44LTE3LjktMTIuMWMtMTAuMy0xMC45LTE0LjEtMjktMTQuMS01Mi45IFY4Ni41aC0zMVY1OC4zaDMxVjkuNkwtNDEzLjcsMEwtNDEzLjcsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOTc0LjQzMzI4NiwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDAuOTkwMDM0LCAwLjYxMDMzOSkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDQ1LjgsMTEzYzAuOCw1MCwzMi4yLDcwLjYsNjguNiw3MC42YzE5LDAuNiwzNy45LTMsNTUuMy0xMC41bDYuMiwyNi40IGMtMjAuOSw4LjktNDMuNSwxMy4xLTY2LjIsMTIuNmMtNjEuNSwwLTk4LjMtNDEuMi05OC4zLTEwMi41Qy00ODAuMiw0OC4yLTQ0NC43LDAtMzg2LjUsMGM2NS4yLDAsODIuNyw1OC4zLDgyLjcsOTUuNyBjLTAuMSw1LjgtMC41LDExLjUtMS4yLDE3LjJoLTE0MC42SC00NDUuOEwtNDQ1LjgsMTEzeiBNLTMzOS4yLDg2LjZjMC40LTIzLjUtOS41LTYwLjEtNTAuNC02MC4xIGMtMzYuOCwwLTUyLjgsMzQuNC01NS43LDYwLjFILTMzOS4yTC0zMzkuMiw4Ni42TC0zMzkuMiw4Ni42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMjAxLjk2MTA1OCwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuMTc5NjQwLCAwLjcwNTA2OCkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDc4LjYsNjhjMC0yMy45LTAuNC00NC41LTEuNy02My40aDMxLjhsMS4yLDM5LjloMS43YzkuMS0yNy4zLDMxLTQ0LjUsNTUuMy00NC41IGMzLjUtMC4xLDcsMC40LDEwLjMsMS4ydjM0LjhjLTQuMS0wLjktOC4yLTEuMy0xMi40LTEuMmMtMjUuNiwwLTQzLjcsMTkuNy00OC43LDQ3LjRjLTEsNS43LTEuNiwxMS41LTEuNywxNy4ydjEwOC4zaC0zNlY2OCBMLTQ3OC42LDY4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCBkPSJNMTM1Mi4zLDMyNi4yaDM3VjI4aC0zN1YzMjYuMnogTTE2MDQuOCwzMjYuMmMtMi41LTEzLjktMy40LTMxLjEtMy40LTQ4Ljd2LTc2IGMwLTQwLjctMTUuMS04My4xLTc3LjMtODMuMWMtMjUuNiwwLTUwLDcuMS02Ni44LDE4LjFsOC40LDI0LjRjMTQuMy05LjIsMzQtMTUuMSw1My0xNS4xYzQxLjYsMCw0Ni4yLDMwLjIsNDYuMiw0N3Y0LjIgYy03OC42LTAuNC0xMjIuMywyNi41LTEyMi4zLDc1LjZjMCwyOS40LDIxLDU4LjQsNjIuMiw1OC40YzI5LDAsNTAuOS0xNC4zLDYyLjItMzAuMmgxLjNsMi45LDI1LjZIMTYwNC44eiBNMTU2NS43LDI1Ny43IGMwLDMuOC0wLjgsOC0yLjEsMTEuOGMtNS45LDE3LjItMjIuNywzNC00OS4yLDM0Yy0xOC45LDAtMzQuOS0xMS4zLTM0LjktMzUuM2MwLTM5LjUsNDUuOC00Ni42LDg2LjItNDUuOFYyNTcuN3ogTTE2OTguNSwzMjYuMiBsMS43LTMzLjZoMS4zYzE1LjEsMjYuOSwzOC43LDM4LjIsNjguMSwzOC4yYzQ1LjQsMCw5MS4yLTM2LjEsOTEuMi0xMDguOGMwLjQtNjEuNy0zNS4zLTEwMy43LTg1LjctMTAzLjcgYy0zMi44LDAtNTYuMywxNC43LTY5LjMsMzcuNGgtMC44VjI4aC0zNi42djI0NS43YzAsMTguMS0wLjgsMzguNi0xLjcsNTIuNUgxNjk4LjV6IE0xNzA0LjgsMjA4LjJjMC01LjksMS4zLTEwLjksMi4xLTE1LjEgYzcuNi0yOC4xLDMxLjEtNDUuNCw1Ni4zLTQ1LjRjMzkuNSwwLDYwLjUsMzQuOSw2MC41LDc1LjZjMCw0Ni42LTIzLjEsNzguMS02MS44LDc4LjFjLTI2LjksMC00OC4zLTE3LjYtNTUuNS00My4zIGMtMC44LTQuMi0xLjctOC44LTEuNy0xMy40VjIwOC4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgZmlsbD0iIzYxNjE2MSIgZD0iTTE1IDlIOXY2aDZWOXptLTIgNGgtMnYtMmgydjJ6bTgtMlY5aC0yVjdjMC0xLjEtLjktMi0yLTJoLTJWM2gtMnYyaC0yVjNIOXYySDdjLTEuMSAwLTIgLjktMiAydjJIM3YyaDJ2MkgzdjJoMnYyYzAgMS4xLjkgMiAyIDJoMnYyaDJ2LTJoMnYyaDJ2LTJoMmMxLjEgMCAyLS45IDItMnYtMmgydi0yaC0ydi0yaDJ6bS00IDZIN1Y3aDEwdjEweiIvPgo8L3N2Zz4K);
  --jp-icon-keyboard: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMTdjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY3YzAtMS4xLS45LTItMi0yem0tOSAzaDJ2MmgtMlY4em0wIDNoMnYyaC0ydi0yek04IDhoMnYySDhWOHptMCAzaDJ2Mkg4di0yem0tMSAySDV2LTJoMnYyem0wLTNINVY4aDJ2MnptOSA3SDh2LTJoOHYyem0wLTRoLTJ2LTJoMnYyem0wLTNoLTJWOGgydjJ6bTMgM2gtMnYtMmgydjJ6bTAtM2gtMlY4aDJ2MnoiLz4KPC9zdmc+Cg==);
  --jp-icon-launcher: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkgMTlINVY1aDdWM0g1YTIgMiAwIDAwLTIgMnYxNGEyIDIgMCAwMDIgMmgxNGMxLjEgMCAyLS45IDItMnYtN2gtMnY3ek0xNCAzdjJoMy41OWwtOS44MyA5LjgzIDEuNDEgMS40MUwxOSA2LjQxVjEwaDJWM2gtN3oiLz4KPC9zdmc+Cg==);
  --jp-icon-line-form: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGZpbGw9IndoaXRlIiBkPSJNNS44OCA0LjEyTDEzLjc2IDEybC03Ljg4IDcuODhMOCAyMmwxMC0xMEw4IDJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-link: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMuOSAxMmMwLTEuNzEgMS4zOS0zLjEgMy4xLTMuMWg0VjdIN2MtMi43NiAwLTUgMi4yNC01IDVzMi4yNCA1IDUgNWg0di0xLjlIN2MtMS43MSAwLTMuMS0xLjM5LTMuMS0zLjF6TTggMTNoOHYtMkg4djJ6bTktNmgtNHYxLjloNGMxLjcxIDAgMy4xIDEuMzkgMy4xIDMuMXMtMS4zOSAzLjEtMy4xIDMuMWgtNFYxN2g0YzIuNzYgMCA1LTIuMjQgNS01cy0yLjI0LTUtNS01eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xOSA1djE0SDVWNWgxNG0xLjEtMkgzLjljLS41IDAtLjkuNC0uOS45djE2LjJjMCAuNC40LjkuOS45aDE2LjJjLjQgMCAuOS0uNS45LS45VjMuOWMwLS41LS41LS45LS45LS45ek0xMSA3aDZ2MmgtNlY3em0wIDRoNnYyaC02di0yem0wIDRoNnYyaC02ek03IDdoMnYySDd6bTAgNGgydjJIN3ptMCA0aDJ2Mkg3eiIvPgo8L3N2Zz4=);
  --jp-icon-listings-info: url(data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iaXNvLTg4NTktMSI/Pg0KPHN2ZyB2ZXJzaW9uPSIxLjEiIGlkPSJDYXBhXzEiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgeG1sbnM6eGxpbms9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkveGxpbmsiIHg9IjBweCIgeT0iMHB4Ig0KCSB2aWV3Qm94PSIwIDAgNTAuOTc4IDUwLjk3OCIgc3R5bGU9ImVuYWJsZS1iYWNrZ3JvdW5kOm5ldyAwIDAgNTAuOTc4IDUwLjk3ODsiIHhtbDpzcGFjZT0icHJlc2VydmUiPg0KPGc+DQoJPGc+DQoJCTxnPg0KCQkJPHBhdGggc3R5bGU9ImZpbGw6IzAxMDAwMjsiIGQ9Ik00My41Miw3LjQ1OEMzOC43MTEsMi42NDgsMzIuMzA3LDAsMjUuNDg5LDBDMTguNjcsMCwxMi4yNjYsMi42NDgsNy40NTgsNy40NTgNCgkJCQljLTkuOTQzLDkuOTQxLTkuOTQzLDI2LjExOSwwLDM2LjA2MmM0LjgwOSw0LjgwOSwxMS4yMTIsNy40NTYsMTguMDMxLDcuNDU4YzAsMCwwLjAwMSwwLDAuMDAyLDANCgkJCQljNi44MTYsMCwxMy4yMjEtMi42NDgsMTguMDI5LTcuNDU4YzQuODA5LTQuODA5LDcuNDU3LTExLjIxMiw3LjQ1Ny0xOC4wM0M1MC45NzcsMTguNjcsNDguMzI4LDEyLjI2Niw0My41Miw3LjQ1OHoNCgkJCQkgTTQyLjEwNiw0Mi4xMDVjLTQuNDMyLDQuNDMxLTEwLjMzMiw2Ljg3Mi0xNi42MTUsNi44NzJoLTAuMDAyYy02LjI4NS0wLjAwMS0xMi4xODctMi40NDEtMTYuNjE3LTYuODcyDQoJCQkJYy05LjE2Mi05LjE2My05LjE2Mi0yNC4wNzEsMC0zMy4yMzNDMTMuMzAzLDQuNDQsMTkuMjA0LDIsMjUuNDg5LDJjNi4yODQsMCwxMi4xODYsMi40NCwxNi42MTcsNi44NzINCgkJCQljNC40MzEsNC40MzEsNi44NzEsMTAuMzMyLDYuODcxLDE2LjYxN0M0OC45NzcsMzEuNzcyLDQ2LjUzNiwzNy42NzUsNDIuMTA2LDQyLjEwNXoiLz4NCgkJPC9nPg0KCQk8Zz4NCgkJCTxwYXRoIHN0eWxlPSJmaWxsOiMwMTAwMDI7IiBkPSJNMjMuNTc4LDMyLjIxOGMtMC4wMjMtMS43MzQsMC4xNDMtMy4wNTksMC40OTYtMy45NzJjMC4zNTMtMC45MTMsMS4xMS0xLjk5NywyLjI3Mi0zLjI1Mw0KCQkJCWMwLjQ2OC0wLjUzNiwwLjkyMy0xLjA2MiwxLjM2Ny0xLjU3NWMwLjYyNi0wLjc1MywxLjEwNC0xLjQ3OCwxLjQzNi0yLjE3NWMwLjMzMS0wLjcwNywwLjQ5NS0xLjU0MSwwLjQ5NS0yLjUNCgkJCQljMC0xLjA5Ni0wLjI2LTIuMDg4LTAuNzc5LTIuOTc5Yy0wLjU2NS0wLjg3OS0xLjUwMS0xLjMzNi0yLjgwNi0xLjM2OWMtMS44MDIsMC4wNTctMi45ODUsMC42NjctMy41NSwxLjgzMg0KCQkJCWMtMC4zMDEsMC41MzUtMC41MDMsMS4xNDEtMC42MDcsMS44MTRjLTAuMTM5LDAuNzA3LTAuMjA3LDEuNDMyLTAuMjA3LDIuMTc0aC0yLjkzN2MtMC4wOTEtMi4yMDgsMC40MDctNC4xMTQsMS40OTMtNS43MTkNCgkJCQljMS4wNjItMS42NCwyLjg1NS0yLjQ4MSw1LjM3OC0yLjUyN2MyLjE2LDAuMDIzLDMuODc0LDAuNjA4LDUuMTQxLDEuNzU4YzEuMjc4LDEuMTYsMS45MjksMi43NjQsMS45NSw0LjgxMQ0KCQkJCWMwLDEuMTQyLTAuMTM3LDIuMTExLTAuNDEsMi45MTFjLTAuMzA5LDAuODQ1LTAuNzMxLDEuNTkzLTEuMjY4LDIuMjQzYy0wLjQ5MiwwLjY1LTEuMDY4LDEuMzE4LTEuNzMsMi4wMDINCgkJCQljLTAuNjUsMC42OTctMS4zMTMsMS40NzktMS45ODcsMi4zNDZjLTAuMjM5LDAuMzc3LTAuNDI5LDAuNzc3LTAuNTY1LDEuMTk5Yy0wLjE2LDAuOTU5LTAuMjE3LDEuOTUxLTAuMTcxLDIuOTc5DQoJCQkJQzI2LjU4OSwzMi4yMTgsMjMuNTc4LDMyLjIxOCwyMy41NzgsMzIuMjE4eiBNMjMuNTc4LDM4LjIydi0zLjQ4NGgzLjA3NnYzLjQ4NEgyMy41Nzh6Ii8+DQoJCTwvZz4NCgk8L2c+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8L3N2Zz4NCg==);
  --jp-icon-markdown: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjN0IxRkEyIiBkPSJNNSAxNC45aDEybC02LjEgNnptOS40LTYuOGMwLTEuMy0uMS0yLjktLjEtNC41LS40IDEuNC0uOSAyLjktMS4zIDQuM2wtMS4zIDQuM2gtMkw4LjUgNy45Yy0uNC0xLjMtLjctMi45LTEtNC4zLS4xIDEuNi0uMSAzLjItLjIgNC42TDcgMTIuNEg0LjhsLjctMTFoMy4zTDEwIDVjLjQgMS4yLjcgMi43IDEgMy45LjMtMS4yLjctMi42IDEtMy45bDEuMi0zLjdoMy4zbC42IDExaC0yLjRsLS4zLTQuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-new-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwIDZoLThsLTItMkg0Yy0xLjExIDAtMS45OS44OS0xLjk5IDJMMiAxOGMwIDEuMTEuODkgMiAyIDJoMTZjMS4xMSAwIDItLjg5IDItMlY4YzAtMS4xMS0uODktMi0yLTJ6bS0xIDhoLTN2M2gtMnYtM2gtM3YtMmgzVjloMnYzaDN2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-not-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI1IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDMgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMTkgMTcuMTg0NCAyLjk2OTY4IDE0LjMwMzIgMS44NjA5NCAxMS40NDA5WiIvPgogICAgPHBhdGggY2xhc3M9ImpwLWljb24yIiBzdHJva2U9IiMzMzMzMzMiIHN0cm9rZS13aWR0aD0iMiIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOS4zMTU5MiA5LjMyMDMxKSIgZD0iTTcuMzY4NDIgMEwwIDcuMzY0NzkiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDkuMzE1OTIgMTYuNjgzNikgc2NhbGUoMSAtMSkiIGQ9Ik03LjM2ODQyIDBMMCA3LjM2NDc5Ii8+Cjwvc3ZnPgo=);
  --jp-icon-notebook: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNFRjZDMDAiPgogICAgPHBhdGggZD0iTTE4LjcgMy4zdjE1LjRIMy4zVjMuM2gxNS40bTEuNS0xLjVIMS44djE4LjNoMTguM2wuMS0xOC4zeiIvPgogICAgPHBhdGggZD0iTTE2LjUgMTYuNWwtNS40LTQuMy01LjYgNC4zdi0xMWgxMXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-palette: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE4IDEzVjIwSDRWNkg5LjAyQzkuMDcgNS4yOSA5LjI0IDQuNjIgOS41IDRINEMyLjkgNCAyIDQuOSAyIDZWMjBDMiAyMS4xIDIuOSAyMiA0IDIySDE4QzE5LjEgMjIgMjAgMjEuMSAyMCAyMFYxNUwxOCAxM1pNMTkuMyA4Ljg5QzE5Ljc0IDguMTkgMjAgNy4zOCAyMCA2LjVDMjAgNC4wMSAxNy45OSAyIDE1LjUgMkMxMy4wMSAyIDExIDQuMDEgMTEgNi41QzExIDguOTkgMTMuMDEgMTEgMTUuNDkgMTFDMTYuMzcgMTEgMTcuMTkgMTAuNzQgMTcuODggMTAuM0wyMSAxMy40MkwyMi40MiAxMkwxOS4zIDguODlaTTE1LjUgOUMxNC4xMiA5IDEzIDcuODggMTMgNi41QzEzIDUuMTIgMTQuMTIgNCAxNS41IDRDMTYuODggNCAxOCA1LjEyIDE4IDYuNUMxOCA3Ljg4IDE2Ljg4IDkgMTUuNSA5WiIvPgogICAgPHBhdGggZmlsbC1ydWxlPSJldmVub2RkIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiIGQ9Ik00IDZIOS4wMTg5NEM5LjAwNjM5IDYuMTY1MDIgOSA2LjMzMTc2IDkgNi41QzkgOC44MTU3NyAxMC4yMTEgMTAuODQ4NyAxMi4wMzQzIDEySDlWMTRIMTZWMTIuOTgxMUMxNi41NzAzIDEyLjkzNzcgMTcuMTIgMTIuODIwNyAxNy42Mzk2IDEyLjYzOTZMMTggMTNWMjBINFY2Wk04IDhINlYxMEg4VjhaTTYgMTJIOFYxNEg2VjEyWk04IDE2SDZWMThIOFYxNlpNOSAxNkgxNlYxOEg5VjE2WiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-paste: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE5IDJoLTQuMThDMTQuNC44NCAxMy4zIDAgMTIgMGMtMS4zIDAtMi40Ljg0LTIuODIgMkg1Yy0xLjEgMC0yIC45LTIgMnYxNmMwIDEuMS45IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjRjMC0xLjEtLjktMi0yLTJ6bS03IDBjLjU1IDAgMSAuNDUgMSAxcy0uNDUgMS0xIDEtMS0uNDUtMS0xIC40NS0xIDEtMXptNyAxOEg1VjRoMnYzaDEwVjRoMnYxNnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-python: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1icmFuZDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMEQ0N0ExIj4KICAgIDxwYXRoIGQ9Ik0xMS4xIDYuOVY1LjhINi45YzAtLjUgMC0xLjMuMi0xLjYuNC0uNy44LTEuMSAxLjctMS40IDEuNy0uMyAyLjUtLjMgMy45LS4xIDEgLjEgMS45LjkgMS45IDEuOXY0LjJjMCAuNS0uOSAxLjYtMiAxLjZIOC44Yy0xLjUgMC0yLjQgMS40LTIuNCAyLjh2Mi4ySDQuN0MzLjUgMTUuMSAzIDE0IDMgMTMuMVY5Yy0uMS0xIC42LTIgMS44LTIgMS41LS4xIDYuMy0uMSA2LjMtLjF6Ii8+CiAgICA8cGF0aCBkPSJNMTAuOSAxNS4xdjEuMWg0LjJjMCAuNSAwIDEuMy0uMiAxLjYtLjQuNy0uOCAxLjEtMS43IDEuNC0xLjcuMy0yLjUuMy0zLjkuMS0xLS4xLTEuOS0uOS0xLjktMS45di00LjJjMC0uNS45LTEuNiAyLTEuNmgzLjhjMS41IDAgMi40LTEuNCAyLjQtMi44VjYuNmgxLjdDMTguNSA2LjkgMTkgOCAxOSA4LjlWMTNjMCAxLS43IDIuMS0xLjkgMi4xaC02LjJ6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-r-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjE5NkYzIiBkPSJNNC40IDIuNWMxLjItLjEgMi45LS4zIDQuOS0uMyAyLjUgMCA0LjEuNCA1LjIgMS4zIDEgLjcgMS41IDEuOSAxLjUgMy41IDAgMi0xLjQgMy41LTIuOSA0LjEgMS4yLjQgMS43IDEuNiAyLjIgMyAuNiAxLjkgMSAzLjkgMS4zIDQuNmgtMy44Yy0uMy0uNC0uOC0xLjctMS4yLTMuN3MtMS4yLTIuNi0yLjYtMi42aC0uOXY2LjRINC40VjIuNXptMy43IDYuOWgxLjRjMS45IDAgMi45LS45IDIuOS0yLjNzLTEtMi4zLTIuOC0yLjNjLS43IDAtMS4zIDAtMS42LjJ2NC41aC4xdi0uMXoiLz4KPC9zdmc+Cg==);
  --jp-icon-react: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMTUwIDE1MCA1NDEuOSAyOTUuMyI+CiAgPGcgY2xhc3M9ImpwLWljb24tYnJhbmQyIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzYxREFGQiI+CiAgICA8cGF0aCBkPSJNNjY2LjMgMjk2LjVjMC0zMi41LTQwLjctNjMuMy0xMDMuMS04Mi40IDE0LjQtNjMuNiA4LTExNC4yLTIwLjItMTMwLjQtNi41LTMuOC0xNC4xLTUuNi0yMi40LTUuNnYyMi4zYzQuNiAwIDguMy45IDExLjQgMi42IDEzLjYgNy44IDE5LjUgMzcuNSAxNC45IDc1LjctMS4xIDkuNC0yLjkgMTkuMy01LjEgMjkuNC0xOS42LTQuOC00MS04LjUtNjMuNS0xMC45LTEzLjUtMTguNS0yNy41LTM1LjMtNDEuNi01MCAzMi42LTMwLjMgNjMuMi00Ni45IDg0LTQ2LjlWNzhjLTI3LjUgMC02My41IDE5LjYtOTkuOSA1My42LTM2LjQtMzMuOC03Mi40LTUzLjItOTkuOS01My4ydjIyLjNjMjAuNyAwIDUxLjQgMTYuNSA4NCA0Ni42LTE0IDE0LjctMjggMzEuNC00MS4zIDQ5LjktMjIuNiAyLjQtNDQgNi4xLTYzLjYgMTEtMi4zLTEwLTQtMTkuNy01LjItMjktNC43LTM4LjIgMS4xLTY3LjkgMTQuNi03NS44IDMtMS44IDYuOS0yLjYgMTEuNS0yLjZWNzguNWMtOC40IDAtMTYgMS44LTIyLjYgNS42LTI4LjEgMTYuMi0zNC40IDY2LjctMTkuOSAxMzAuMS02Mi4yIDE5LjItMTAyLjcgNDkuOS0xMDIuNyA4Mi4zIDAgMzIuNSA0MC43IDYzLjMgMTAzLjEgODIuNC0xNC40IDYzLjYtOCAxMTQuMiAyMC4yIDEzMC40IDYuNSAzLjggMTQuMSA1LjYgMjIuNSA1LjYgMjcuNSAwIDYzLjUtMTkuNiA5OS45LTUzLjYgMzYuNCAzMy44IDcyLjQgNTMuMiA5OS45IDUzLjIgOC40IDAgMTYtMS44IDIyLjYtNS42IDI4LjEtMTYuMiAzNC40LTY2LjcgMTkuOS0xMzAuMSA2Mi0xOS4xIDEwMi41LTQ5LjkgMTAyLjUtODIuM3ptLTEzMC4yLTY2LjdjLTMuNyAxMi45LTguMyAyNi4yLTEzLjUgMzkuNS00LjEtOC04LjQtMTYtMTMuMS0yNC00LjYtOC05LjUtMTUuOC0xNC40LTIzLjQgMTQuMiAyLjEgMjcuOSA0LjcgNDEgNy45em0tNDUuOCAxMDYuNWMtNy44IDEzLjUtMTUuOCAyNi4zLTI0LjEgMzguMi0xNC45IDEuMy0zMCAyLTQ1LjIgMi0xNS4xIDAtMzAuMi0uNy00NS0xLjktOC4zLTExLjktMTYuNC0yNC42LTI0LjItMzgtNy42LTEzLjEtMTQuNS0yNi40LTIwLjgtMzkuOCA2LjItMTMuNCAxMy4yLTI2LjggMjAuNy0zOS45IDcuOC0xMy41IDE1LjgtMjYuMyAyNC4xLTM4LjIgMTQuOS0xLjMgMzAtMiA0NS4yLTIgMTUuMSAwIDMwLjIuNyA0NSAxLjkgOC4zIDExLjkgMTYuNCAyNC42IDI0LjIgMzggNy42IDEzLjEgMTQuNSAyNi40IDIwLjggMzkuOC02LjMgMTMuNC0xMy4yIDI2LjgtMjAuNyAzOS45em0zMi4zLTEzYzUuNCAxMy40IDEwIDI2LjggMTMuOCAzOS44LTEzLjEgMy4yLTI2LjkgNS45LTQxLjIgOCA0LjktNy43IDkuOC0xNS42IDE0LjQtMjMuNyA0LjYtOCA4LjktMTYuMSAxMy0yNC4xek00MjEuMiA0MzBjLTkuMy05LjYtMTguNi0yMC4zLTI3LjgtMzIgOSAuNCAxOC4yLjcgMjcuNS43IDkuNCAwIDE4LjctLjIgMjcuOC0uNy05IDExLjctMTguMyAyMi40LTI3LjUgMzJ6bS03NC40LTU4LjljLTE0LjItMi4xLTI3LjktNC43LTQxLTcuOSAzLjctMTIuOSA4LjMtMjYuMiAxMy41LTM5LjUgNC4xIDggOC40IDE2IDEzLjEgMjQgNC43IDggOS41IDE1LjggMTQuNCAyMy40ek00MjAuNyAxNjNjOS4zIDkuNiAxOC42IDIwLjMgMjcuOCAzMi05LS40LTE4LjItLjctMjcuNS0uNy05LjQgMC0xOC43LjItMjcuOC43IDktMTEuNyAxOC4zLTIyLjQgMjcuNS0zMnptLTc0IDU4LjljLTQuOSA3LjctOS44IDE1LjYtMTQuNCAyMy43LTQuNiA4LTguOSAxNi0xMyAyNC01LjQtMTMuNC0xMC0yNi44LTEzLjgtMzkuOCAxMy4xLTMuMSAyNi45LTUuOCA0MS4yLTcuOXptLTkwLjUgMTI1LjJjLTM1LjQtMTUuMS01OC4zLTM0LjktNTguMy01MC42IDAtMTUuNyAyMi45LTM1LjYgNTguMy01MC42IDguNi0zLjcgMTgtNyAyNy43LTEwLjEgNS43IDE5LjYgMTMuMiA0MCAyMi41IDYwLjktOS4yIDIwLjgtMTYuNiA0MS4xLTIyLjIgNjAuNi05LjktMy4xLTE5LjMtNi41LTI4LTEwLjJ6TTMxMCA0OTBjLTEzLjYtNy44LTE5LjUtMzcuNS0xNC45LTc1LjcgMS4xLTkuNCAyLjktMTkuMyA1LjEtMjkuNCAxOS42IDQuOCA0MSA4LjUgNjMuNSAxMC45IDEzLjUgMTguNSAyNy41IDM1LjMgNDEuNiA1MC0zMi42IDMwLjMtNjMuMiA0Ni45LTg0IDQ2LjktNC41LS4xLTguMy0xLTExLjMtMi43em0yMzcuMi03Ni4yYzQuNyAzOC4yLTEuMSA2Ny45LTE0LjYgNzUuOC0zIDEuOC02LjkgMi42LTExLjUgMi42LTIwLjcgMC01MS40LTE2LjUtODQtNDYuNiAxNC0xNC43IDI4LTMxLjQgNDEuMy00OS45IDIyLjYtMi40IDQ0LTYuMSA2My42LTExIDIuMyAxMC4xIDQuMSAxOS44IDUuMiAyOS4xem0zOC41LTY2LjdjLTguNiAzLjctMTggNy0yNy43IDEwLjEtNS43LTE5LjYtMTMuMi00MC0yMi41LTYwLjkgOS4yLTIwLjggMTYuNi00MS4xIDIyLjItNjAuNiA5LjkgMy4xIDE5LjMgNi41IDI4LjEgMTAuMiAzNS40IDE1LjEgNTguMyAzNC45IDU4LjMgNTAuNi0uMSAxNS43LTIzIDM1LjYtNTguNCA1MC42ek0zMjAuOCA3OC40eiIvPgogICAgPGNpcmNsZSBjeD0iNDIwLjkiIGN5PSIyOTYuNSIgcj0iNDUuNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-refresh: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTkgMTMuNWMtMi40OSAwLTQuNS0yLjAxLTQuNS00LjVTNi41MSA0LjUgOSA0LjVjMS4yNCAwIDIuMzYuNTIgMy4xNyAxLjMzTDEwIDhoNVYzbC0xLjc2IDEuNzZDMTIuMTUgMy42OCAxMC42NiAzIDkgMyA1LjY5IDMgMy4wMSA1LjY5IDMuMDEgOVM1LjY5IDE1IDkgMTVjMi45NyAwIDUuNDMtMi4xNiA1LjktNWgtMS41MmMtLjQ2IDItMi4yNCAzLjUtNC4zOCAzLjV6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-regex: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi1hY2NlbnQyIiBmaWxsPSIjRkZGIj4KICAgIDxjaXJjbGUgY2xhc3M9InN0MiIgY3g9IjUuNSIgY3k9IjE0LjUiIHI9IjEuNSIvPgogICAgPHJlY3QgeD0iMTIiIHk9IjQiIGNsYXNzPSJzdDIiIHdpZHRoPSIxIiBoZWlnaHQ9IjgiLz4KICAgIDxyZWN0IHg9IjguNSIgeT0iNy41IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjg2NiAtMC41IDAuNSAwLjg2NiAtMi4zMjU1IDcuMzIxOSkiIGNsYXNzPSJzdDIiIHdpZHRoPSI4IiBoZWlnaHQ9IjEiLz4KICAgIDxyZWN0IHg9IjEyIiB5PSI0IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjUgLTAuODY2IDAuODY2IDAuNSAtMC42Nzc5IDE0LjgyNTIpIiBjbGFzcz0ic3QyIiB3aWR0aD0iMSIgaGVpZ2h0PSI4Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-run: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTggNXYxNGwxMS03eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-running: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMjU2IDhDMTE5IDggOCAxMTkgOCAyNTZzMTExIDI0OCAyNDggMjQ4IDI0OC0xMTEgMjQ4LTI0OFMzOTMgOCAyNTYgOHptOTYgMzI4YzAgOC44LTcuMiAxNi0xNiAxNkgxNzZjLTguOCAwLTE2LTcuMi0xNi0xNlYxNzZjMC04LjggNy4yLTE2IDE2LTE2aDE2MGM4LjggMCAxNiA3LjIgMTYgMTZ2MTYweiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-save: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE3IDNINWMtMS4xMSAwLTIgLjktMiAydjE0YzAgMS4xLjg5IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjdsLTQtNHptLTUgMTZjLTEuNjYgMC0zLTEuMzQtMy0zczEuMzQtMyAzLTMgMyAxLjM0IDMgMy0xLjM0IDMtMyAzem0zLTEwSDVWNWgxMHY0eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-search: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjEsMTAuOWgtMC43bC0wLjItMC4yYzAuOC0wLjksMS4zLTIuMiwxLjMtMy41YzAtMy0yLjQtNS40LTUuNC01LjRTMS44LDQuMiwxLjgsNy4xczIuNCw1LjQsNS40LDUuNCBjMS4zLDAsMi41LTAuNSwzLjUtMS4zbDAuMiwwLjJ2MC43bDQuMSw0LjFsMS4yLTEuMkwxMi4xLDEwLjl6IE03LjEsMTAuOWMtMi4xLDAtMy43LTEuNy0zLjctMy43czEuNy0zLjcsMy43LTMuN3MzLjcsMS43LDMuNywzLjcgUzkuMiwxMC45LDcuMSwxMC45eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-settings: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuNDMgMTIuOThjLjA0LS4zMi4wNy0uNjQuMDctLjk4cy0uMDMtLjY2LS4wNy0uOThsMi4xMS0xLjY1Yy4xOS0uMTUuMjQtLjQyLjEyLS42NGwtMi0zLjQ2Yy0uMTItLjIyLS4zOS0uMy0uNjEtLjIybC0yLjQ5IDFjLS41Mi0uNC0xLjA4LS43My0xLjY5LS45OGwtLjM4LTIuNjVBLjQ4OC40ODggMCAwMDE0IDJoLTRjLS4yNSAwLS40Ni4xOC0uNDkuNDJsLS4zOCAyLjY1Yy0uNjEuMjUtMS4xNy41OS0xLjY5Ljk4bC0yLjQ5LTFjLS4yMy0uMDktLjQ5IDAtLjYxLjIybC0yIDMuNDZjLS4xMy4yMi0uMDcuNDkuMTIuNjRsMi4xMSAxLjY1Yy0uMDQuMzItLjA3LjY1LS4wNy45OHMuMDMuNjYuMDcuOThsLTIuMTEgMS42NWMtLjE5LjE1LS4yNC40Mi0uMTIuNjRsMiAzLjQ2Yy4xMi4yMi4zOS4zLjYxLjIybDIuNDktMWMuNTIuNCAxLjA4LjczIDEuNjkuOThsLjM4IDIuNjVjLjAzLjI0LjI0LjQyLjQ5LjQyaDRjLjI1IDAgLjQ2LS4xOC40OS0uNDJsLjM4LTIuNjVjLjYxLS4yNSAxLjE3LS41OSAxLjY5LS45OGwyLjQ5IDFjLjIzLjA5LjQ5IDAgLjYxLS4yMmwyLTMuNDZjLjEyLS4yMi4wNy0uNDktLjEyLS42NGwtMi4xMS0xLjY1ek0xMiAxNS41Yy0xLjkzIDAtMy41LTEuNTctMy41LTMuNXMxLjU3LTMuNSAzLjUtMy41IDMuNSAxLjU3IDMuNSAzLjUtMS41NyAzLjUtMy41IDMuNXoiLz4KPC9zdmc+Cg==);
  --jp-icon-spreadsheet: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNENBRjUwIiBkPSJNMi4yIDIuMnYxNy42aDE3LjZWMi4ySDIuMnptMTUuNCA3LjdoLTUuNVY0LjRoNS41djUuNXpNOS45IDQuNHY1LjVINC40VjQuNGg1LjV6bS01LjUgNy43aDUuNXY1LjVINC40di01LjV6bTcuNyA1LjV2LTUuNWg1LjV2NS41aC01LjV6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-stop: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik02IDZoMTJ2MTJINnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-tab: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIxIDNIM2MtMS4xIDAtMiAuOS0yIDJ2MTRjMCAxLjEuOSAyIDIgMmgxOGMxLjEgMCAyLS45IDItMlY1YzAtMS4xLS45LTItMi0yem0wIDE2SDNWNWgxMHY0aDh2MTB6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-terminal: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0IiA+CiAgICA8cmVjdCBjbGFzcz0ianAtaWNvbjIganAtaWNvbi1zZWxlY3RhYmxlIiB3aWR0aD0iMjAiIGhlaWdodD0iMjAiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIgMikiIGZpbGw9IiMzMzMzMzMiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uLWFjY2VudDIganAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGQ9Ik01LjA1NjY0IDguNzYxNzJDNS4wNTY2NCA4LjU5NzY2IDUuMDMxMjUgOC40NTMxMiA0Ljk4MDQ3IDguMzI4MTJDNC45MzM1OSA4LjE5OTIyIDQuODU1NDcgOC4wODIwMyA0Ljc0NjA5IDcuOTc2NTZDNC42NDA2MiA3Ljg3MTA5IDQuNSA3Ljc3NTM5IDQuMzI0MjIgNy42ODk0NUM0LjE1MjM0IDcuNTk5NjEgMy45NDMzNiA3LjUxMTcyIDMuNjk3MjcgNy40MjU3OEMzLjMwMjczIDcuMjg1MTYgMi45NDMzNiA3LjEzNjcyIDIuNjE5MTQgNi45ODA0N0MyLjI5NDkyIDYuODI0MjIgMi4wMTc1OCA2LjY0MjU4IDEuNzg3MTEgNi40MzU1NUMxLjU2MDU1IDYuMjI4NTIgMS4zODQ3NyA1Ljk4ODI4IDEuMjU5NzcgNS43MTQ4NEMxLjEzNDc3IDUuNDM3NSAxLjA3MjI3IDUuMTA5MzggMS4wNzIyNyA0LjczMDQ3QzEuMDcyMjcgNC4zOTg0NCAxLjEyODkxIDQuMDk1NyAxLjI0MjE5IDMuODIyMjdDMS4zNTU0NyAzLjU0NDkyIDEuNTE1NjIgMy4zMDQ2OSAxLjcyMjY2IDMuMTAxNTZDMS45Mjk2OSAyLjg5ODQ0IDIuMTc5NjkgMi43MzQzNyAyLjQ3MjY2IDIuNjA5MzhDMi43NjU2MiAyLjQ4NDM4IDMuMDkxOCAyLjQwNDMgMy40NTExNyAyLjM2OTE0VjEuMTA5MzhINC4zODg2N1YyLjM4MDg2QzQuNzQwMjMgMi40Mjc3MyA1LjA1NjY0IDIuNTIzNDQgNS4zMzc4OSAyLjY2Nzk3QzUuNjE5MTQgMi44MTI1IDUuODU3NDIgMy4wMDE5NSA2LjA1MjczIDMuMjM2MzNDNi4yNTE5NSAzLjQ2NjggNi40MDQzIDMuNzQwMjMgNi41MDk3NyA0LjA1NjY0QzYuNjE5MTQgNC4zNjkxNCA2LjY3MzgzIDQuNzIwNyA2LjY3MzgzIDUuMTExMzNINS4wNDQ5MkM1LjA0NDkyIDQuNjM4NjcgNC45Mzc1IDQuMjgxMjUgNC43MjI2NiA0LjAzOTA2QzQuNTA3ODEgMy43OTI5NyA0LjIxNjggMy42Njk5MiAzLjg0OTYxIDMuNjY5OTJDMy42NTAzOSAzLjY2OTkyIDMuNDc2NTYgMy42OTcyNyAzLjMyODEyIDMuNzUxOTVDMy4xODM1OSAzLjgwMjczIDMuMDY0NDUgMy44NzY5NSAyLjk3MDcgMy45NzQ2MUMyLjg3Njk1IDQuMDY4MzYgMi44MDY2NCA0LjE3OTY5IDIuNzU5NzcgNC4zMDg1OUMyLjcxNjggNC40Mzc1IDIuNjk1MzEgNC41NzgxMiAyLjY5NTMxIDQuNzMwNDdDMi42OTUzMSA0Ljg4MjgxIDIuNzE2OCA1LjAxOTUzIDIuNzU5NzcgNS4xNDA2MkMyLjgwNjY0IDUuMjU3ODEgMi44ODI4MSA1LjM2NzE5IDIuOTg4MjggNS40Njg3NUMzLjA5NzY2IDUuNTcwMzEgMy4yNDAyMyA1LjY2Nzk3IDMuNDE2MDIgNS43NjE3MkMzLjU5MTggNS44NTE1NiAzLjgxMDU1IDUuOTQzMzYgNC4wNzIyNyA2LjAzNzExQzQuNDY2OCA2LjE4NTU1IDQuODI0MjIgNi4zMzk4NCA1LjE0NDUzIDYuNUM1LjQ2NDg0IDYuNjU2MjUgNS43MzgyOCA2LjgzOTg0IDUuOTY0ODQgNy4wNTA3OEM2LjE5NTMxIDcuMjU3ODEgNi4zNzEwOSA3LjUgNi40OTIxOSA3Ljc3NzM0QzYuNjE3MTkgOC4wNTA3OCA2LjY3OTY5IDguMzc1IDYuNjc5NjkgOC43NUM2LjY3OTY5IDkuMDkzNzUgNi42MjMwNSA5LjQwNDMgNi41MDk3NyA5LjY4MTY0QzYuMzk2NDggOS45NTUwOCA2LjIzNDM4IDEwLjE5MTQgNi4wMjM0NCAxMC4zOTA2QzUuODEyNSAxMC41ODk4IDUuNTU4NTkgMTAuNzUgNS4yNjE3MiAxMC44NzExQzQuOTY0ODQgMTAuOTg4MyA0LjYzMjgxIDExLjA2NDUgNC4yNjU2MiAxMS4wOTk2VjEyLjI0OEgzLjMzMzk4VjExLjA5OTZDMy4wMDE5NSAxMS4wNjg0IDIuNjc5NjkgMTAuOTk2MSAyLjM2NzE5IDEwLjg4MjhDMi4wNTQ2OSAxMC43NjU2IDEuNzc3MzQgMTAuNTk3NyAxLjUzNTE2IDEwLjM3ODlDMS4yOTY4OCAxMC4xNjAyIDEuMTA1NDcgOS44ODQ3NyAwLjk2MDkzOCA5LjU1MjczQzAuODE2NDA2IDkuMjE2OCAwLjc0NDE0MSA4LjgxNDQ1IDAuNzQ0MTQxIDguMzQ1N0gyLjM3ODkxQzIuMzc4OTEgOC42MjY5NSAyLjQxOTkyIDguODYzMjggMi41MDE5NSA5LjA1NDY5QzIuNTgzOTggOS4yNDIxOSAyLjY4OTQ1IDkuMzkyNTggMi44MTgzNiA5LjUwNTg2QzIuOTUxMTcgOS42MTUyMyAzLjEwMTU2IDkuNjkzMzYgMy4yNjk1MyA5Ljc0MDIzQzMuNDM3NSA5Ljc4NzExIDMuNjA5MzggOS44MTA1NSAzLjc4NTE2IDkuODEwNTVDNC4yMDMxMiA5LjgxMDU1IDQuNTE5NTMgOS43MTI4OSA0LjczNDM4IDkuNTE3NThDNC45NDkyMiA5LjMyMjI3IDUuMDU2NjQgOS4wNzAzMSA1LjA1NjY0IDguNzYxNzJaTTEzLjQxOCAxMi4yNzE1SDguMDc0MjJWMTFIMTMuNDE4VjEyLjI3MTVaIiB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzLjk1MjY0IDYpIiBmaWxsPSJ3aGl0ZSIvPgo8L3N2Zz4K);
  --jp-icon-text-editor: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTUgMTVIM3YyaDEydi0yem0wLThIM3YyaDEyVjd6TTMgMTNoMTh2LTJIM3Yyem0wIDhoMTh2LTJIM3Yyek0zIDN2MmgxOFYzSDN6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMiAxNy4xODQ0IDIuOTY5NjggMTQuMzAzMiAxLjg2MDk0IDExLjQ0MDlaIi8+CiAgICA8cGF0aCBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiMzMzMzMzMiIHN0cm9rZT0iIzMzMzMzMyIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOCA5Ljg2NzE5KSIgZD0iTTIuODYwMTUgNC44NjUzNUwwLjcyNjU0OSAyLjk5OTU5TDAgMy42MzA0NUwyLjg2MDE1IDYuMTMxNTdMOCAwLjYzMDg3Mkw3LjI3ODU3IDBMMi44NjAxNSA0Ljg2NTM1WiIvPgo8L3N2Zz4K);
  --jp-icon-undo: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjUgOGMtMi42NSAwLTUuMDUuOTktNi45IDIuNkwyIDd2OWg5bC0zLjYyLTMuNjJjMS4zOS0xLjE2IDMuMTYtMS44OCA1LjEyLTEuODggMy41NCAwIDYuNTUgMi4zMSA3LjYgNS41bDIuMzctLjc4QzIxLjA4IDExLjAzIDE3LjE1IDggMTIuNSA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-vega: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbjEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjEyMTIxIj4KICAgIDxwYXRoIGQ9Ik0xMC42IDUuNGwyLjItMy4ySDIuMnY3LjNsNC02LjZ6Ii8+CiAgICA8cGF0aCBkPSJNMTUuOCAyLjJsLTQuNCA2LjZMNyA2LjNsLTQuOCA4djUuNWgxNy42VjIuMmgtNHptLTcgMTUuNEg1LjV2LTQuNGgzLjN2NC40em00LjQgMEg5LjhWOS44aDMuNHY3Ljh6bTQuNCAwaC0zLjRWNi41aDMuNHYxMS4xeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-yaml: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1jb250cmFzdDIganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjRDgxQjYwIj4KICAgIDxwYXRoIGQ9Ik03LjIgMTguNnYtNS40TDMgNS42aDMuM2wxLjQgMy4xYy4zLjkuNiAxLjYgMSAyLjUuMy0uOC42LTEuNiAxLTIuNWwxLjQtMy4xaDMuNGwtNC40IDcuNnY1LjVsLTIuOS0uMXoiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxNi41IiByPSIyLjEiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxMSIgcj0iMi4xIi8+CiAgPC9nPgo8L3N2Zz4K);
}

/* Icon CSS class declarations */

.jp-AddIcon {
  background-image: var(--jp-icon-add);
}
.jp-BugIcon {
  background-image: var(--jp-icon-bug);
}
.jp-BuildIcon {
  background-image: var(--jp-icon-build);
}
.jp-CaretDownEmptyIcon {
  background-image: var(--jp-icon-caret-down-empty);
}
.jp-CaretDownEmptyThinIcon {
  background-image: var(--jp-icon-caret-down-empty-thin);
}
.jp-CaretDownIcon {
  background-image: var(--jp-icon-caret-down);
}
.jp-CaretLeftIcon {
  background-image: var(--jp-icon-caret-left);
}
.jp-CaretRightIcon {
  background-image: var(--jp-icon-caret-right);
}
.jp-CaretUpEmptyThinIcon {
  background-image: var(--jp-icon-caret-up-empty-thin);
}
.jp-CaretUpIcon {
  background-image: var(--jp-icon-caret-up);
}
.jp-CaseSensitiveIcon {
  background-image: var(--jp-icon-case-sensitive);
}
.jp-CheckIcon {
  background-image: var(--jp-icon-check);
}
.jp-CircleEmptyIcon {
  background-image: var(--jp-icon-circle-empty);
}
.jp-CircleIcon {
  background-image: var(--jp-icon-circle);
}
.jp-ClearIcon {
  background-image: var(--jp-icon-clear);
}
.jp-CloseIcon {
  background-image: var(--jp-icon-close);
}
.jp-ConsoleIcon {
  background-image: var(--jp-icon-console);
}
.jp-CopyIcon {
  background-image: var(--jp-icon-copy);
}
.jp-CutIcon {
  background-image: var(--jp-icon-cut);
}
.jp-DownloadIcon {
  background-image: var(--jp-icon-download);
}
.jp-EditIcon {
  background-image: var(--jp-icon-edit);
}
.jp-EllipsesIcon {
  background-image: var(--jp-icon-ellipses);
}
.jp-ExtensionIcon {
  background-image: var(--jp-icon-extension);
}
.jp-FastForwardIcon {
  background-image: var(--jp-icon-fast-forward);
}
.jp-FileIcon {
  background-image: var(--jp-icon-file);
}
.jp-FileUploadIcon {
  background-image: var(--jp-icon-file-upload);
}
.jp-FilterListIcon {
  background-image: var(--jp-icon-filter-list);
}
.jp-FolderIcon {
  background-image: var(--jp-icon-folder);
}
.jp-Html5Icon {
  background-image: var(--jp-icon-html5);
}
.jp-ImageIcon {
  background-image: var(--jp-icon-image);
}
.jp-InspectorIcon {
  background-image: var(--jp-icon-inspector);
}
.jp-JsonIcon {
  background-image: var(--jp-icon-json);
}
.jp-JupyterFaviconIcon {
  background-image: var(--jp-icon-jupyter-favicon);
}
.jp-JupyterIcon {
  background-image: var(--jp-icon-jupyter);
}
.jp-JupyterlabWordmarkIcon {
  background-image: var(--jp-icon-jupyterlab-wordmark);
}
.jp-KernelIcon {
  background-image: var(--jp-icon-kernel);
}
.jp-KeyboardIcon {
  background-image: var(--jp-icon-keyboard);
}
.jp-LauncherIcon {
  background-image: var(--jp-icon-launcher);
}
.jp-LineFormIcon {
  background-image: var(--jp-icon-line-form);
}
.jp-LinkIcon {
  background-image: var(--jp-icon-link);
}
.jp-ListIcon {
  background-image: var(--jp-icon-list);
}
.jp-ListingsInfoIcon {
  background-image: var(--jp-icon-listings-info);
}
.jp-MarkdownIcon {
  background-image: var(--jp-icon-markdown);
}
.jp-NewFolderIcon {
  background-image: var(--jp-icon-new-folder);
}
.jp-NotTrustedIcon {
  background-image: var(--jp-icon-not-trusted);
}
.jp-NotebookIcon {
  background-image: var(--jp-icon-notebook);
}
.jp-PaletteIcon {
  background-image: var(--jp-icon-palette);
}
.jp-PasteIcon {
  background-image: var(--jp-icon-paste);
}
.jp-PythonIcon {
  background-image: var(--jp-icon-python);
}
.jp-RKernelIcon {
  background-image: var(--jp-icon-r-kernel);
}
.jp-ReactIcon {
  background-image: var(--jp-icon-react);
}
.jp-RefreshIcon {
  background-image: var(--jp-icon-refresh);
}
.jp-RegexIcon {
  background-image: var(--jp-icon-regex);
}
.jp-RunIcon {
  background-image: var(--jp-icon-run);
}
.jp-RunningIcon {
  background-image: var(--jp-icon-running);
}
.jp-SaveIcon {
  background-image: var(--jp-icon-save);
}
.jp-SearchIcon {
  background-image: var(--jp-icon-search);
}
.jp-SettingsIcon {
  background-image: var(--jp-icon-settings);
}
.jp-SpreadsheetIcon {
  background-image: var(--jp-icon-spreadsheet);
}
.jp-StopIcon {
  background-image: var(--jp-icon-stop);
}
.jp-TabIcon {
  background-image: var(--jp-icon-tab);
}
.jp-TerminalIcon {
  background-image: var(--jp-icon-terminal);
}
.jp-TextEditorIcon {
  background-image: var(--jp-icon-text-editor);
}
.jp-TrustedIcon {
  background-image: var(--jp-icon-trusted);
}
.jp-UndoIcon {
  background-image: var(--jp-icon-undo);
}
.jp-VegaIcon {
  background-image: var(--jp-icon-vega);
}
.jp-YamlIcon {
  background-image: var(--jp-icon-yaml);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

:root {
  --jp-icon-search-white: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjEsMTAuOWgtMC43bC0wLjItMC4yYzAuOC0wLjksMS4zLTIuMiwxLjMtMy41YzAtMy0yLjQtNS40LTUuNC01LjRTMS44LDQuMiwxLjgsNy4xczIuNCw1LjQsNS40LDUuNCBjMS4zLDAsMi41LTAuNSwzLjUtMS4zbDAuMiwwLjJ2MC43bDQuMSw0LjFsMS4yLTEuMkwxMi4xLDEwLjl6IE03LjEsMTAuOWMtMi4xLDAtMy43LTEuNy0zLjctMy43czEuNy0zLjcsMy43LTMuN3MzLjcsMS43LDMuNywzLjcgUzkuMiwxMC45LDcuMSwxMC45eiIvPgogIDwvZz4KPC9zdmc+Cg==);
}

.jp-Icon,
.jp-MaterialIcon {
  background-position: center;
  background-repeat: no-repeat;
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-cover {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

/**
 * (DEPRECATED) Support for specific CSS icon sizes
 */

.jp-Icon-16 {
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-18 {
  background-size: 18px;
  min-width: 18px;
  min-height: 18px;
}

.jp-Icon-20 {
  background-size: 20px;
  min-width: 20px;
  min-height: 20px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for icons as inline SVG HTMLElements
 */

/* recolor the primary elements of an icon */
.jp-icon0[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon1[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon2[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon3[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}
/* recolor the accent elements of an icon */
.jp-icon-accent0[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-accent1[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-accent2[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-accent3[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-accent4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-accent0[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-accent1[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-accent2[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-accent3[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-accent4[stroke] {
  stroke: var(--jp-layout-color4);
}
/* set the color of an icon to transparent */
.jp-icon-none[fill] {
  fill: none;
}

.jp-icon-none[stroke] {
  stroke: none;
}
/* brand icon colors. Same for light and dark */
.jp-icon-brand0[fill] {
  fill: var(--jp-brand-color0);
}
.jp-icon-brand1[fill] {
  fill: var(--jp-brand-color1);
}
.jp-icon-brand2[fill] {
  fill: var(--jp-brand-color2);
}
.jp-icon-brand3[fill] {
  fill: var(--jp-brand-color3);
}
.jp-icon-brand4[fill] {
  fill: var(--jp-brand-color4);
}

.jp-icon-brand0[stroke] {
  stroke: var(--jp-brand-color0);
}
.jp-icon-brand1[stroke] {
  stroke: var(--jp-brand-color1);
}
.jp-icon-brand2[stroke] {
  stroke: var(--jp-brand-color2);
}
.jp-icon-brand3[stroke] {
  stroke: var(--jp-brand-color3);
}
.jp-icon-brand4[stroke] {
  stroke: var(--jp-brand-color4);
}
/* warn icon colors. Same for light and dark */
.jp-icon-warn0[fill] {
  fill: var(--jp-warn-color0);
}
.jp-icon-warn1[fill] {
  fill: var(--jp-warn-color1);
}
.jp-icon-warn2[fill] {
  fill: var(--jp-warn-color2);
}
.jp-icon-warn3[fill] {
  fill: var(--jp-warn-color3);
}

.jp-icon-warn0[stroke] {
  stroke: var(--jp-warn-color0);
}
.jp-icon-warn1[stroke] {
  stroke: var(--jp-warn-color1);
}
.jp-icon-warn2[stroke] {
  stroke: var(--jp-warn-color2);
}
.jp-icon-warn3[stroke] {
  stroke: var(--jp-warn-color3);
}
/* icon colors that contrast well with each other and most backgrounds */
.jp-icon-contrast0[fill] {
  fill: var(--jp-icon-contrast-color0);
}
.jp-icon-contrast1[fill] {
  fill: var(--jp-icon-contrast-color1);
}
.jp-icon-contrast2[fill] {
  fill: var(--jp-icon-contrast-color2);
}
.jp-icon-contrast3[fill] {
  fill: var(--jp-icon-contrast-color3);
}

.jp-icon-contrast0[stroke] {
  stroke: var(--jp-icon-contrast-color0);
}
.jp-icon-contrast1[stroke] {
  stroke: var(--jp-icon-contrast-color1);
}
.jp-icon-contrast2[stroke] {
  stroke: var(--jp-icon-contrast-color2);
}
.jp-icon-contrast3[stroke] {
  stroke: var(--jp-icon-contrast-color3);
}

/* CSS for icons in selected items in the settings editor */
#setting-editor .jp-PluginList .jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}
#setting-editor
  .jp-PluginList
  .jp-mod-selected
  .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* CSS for icons in selected filebrowser listing items */
.jp-DirListing-item.jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}
.jp-DirListing-item.jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* CSS for icons in selected tabs in the sidebar tab manager */
#tab-manager .lm-TabBar-tab.jp-mod-active .jp-icon-selectable[fill] {
  fill: #fff;
}

#tab-manager .lm-TabBar-tab.jp-mod-active .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}
#tab-manager
  .lm-TabBar-tab.jp-mod-active
  .jp-icon-hover
  :hover
  .jp-icon-selectable[fill] {
  fill: var(--jp-brand-color1);
}

#tab-manager
  .lm-TabBar-tab.jp-mod-active
  .jp-icon-hover
  :hover
  .jp-icon-selectable-inverse[fill] {
  fill: #fff;
}

/**
 * TODO: come up with non css-hack solution for showing the busy icon on top
 *  of the close icon
 * CSS for complex behavior of close icon of tabs in the sidebar tab manager
 */
#tab-manager
  .lm-TabBar-tab.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon3[fill] {
  fill: none;
}
#tab-manager
  .lm-TabBar-tab.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: var(--jp-inverse-layout-color3);
}

#tab-manager
  .lm-TabBar-tab.jp-mod-dirty.jp-mod-active
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: #fff;
}

/**
* TODO: come up with non css-hack solution for showing the busy icon on top
*  of the close icon
* CSS for complex behavior of close icon of tabs in the main area tabbar
*/
.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon3[fill] {
  fill: none;
}
.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: var(--jp-inverse-layout-color3);
}

/* CSS for icons in status bar */
#jp-main-statusbar .jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}

#jp-main-statusbar .jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}
/* special handling for splash icon CSS. While the theme CSS reloads during
   splash, the splash icon can loose theming. To prevent that, we set a
   default for its color variable */
:root {
  --jp-warn-color0: var(--md-orange-700);
}

/* not sure what to do with this one, used in filebrowser listing */
.jp-DragIcon {
  margin-right: 4px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for alt colors for icons as inline SVG HTMLElements
 */

/* alt recolor the primary elements of an icon */
.jp-icon-alt .jp-icon0[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-alt .jp-icon1[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-alt .jp-icon2[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-alt .jp-icon3[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-alt .jp-icon4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-alt .jp-icon0[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-alt .jp-icon1[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-alt .jp-icon2[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-alt .jp-icon3[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-alt .jp-icon4[stroke] {
  stroke: var(--jp-layout-color4);
}

/* alt recolor the accent elements of an icon */
.jp-icon-alt .jp-icon-accent0[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-alt .jp-icon-accent1[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-alt .jp-icon-accent2[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-alt .jp-icon-accent3[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-alt .jp-icon-accent4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-alt .jp-icon-accent0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-alt .jp-icon-accent1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-alt .jp-icon-accent2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-alt .jp-icon-accent3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-alt .jp-icon-accent4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-icon-hoverShow:not(:hover) svg {
  display: none !important;
}

/**
 * Support for hover colors for icons as inline SVG HTMLElements
 */

/**
 * regular colors
 */

/* recolor the primary elements of an icon */
.jp-icon-hover :hover .jp-icon0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-hover :hover .jp-icon1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-hover :hover .jp-icon2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-hover :hover .jp-icon3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-hover :hover .jp-icon4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-hover :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-hover :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-hover :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-hover :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/* recolor the accent elements of an icon */
.jp-icon-hover :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-hover :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-hover :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-hover :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-hover :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-hover :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-hover :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-hover :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-hover :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* set the color of an icon to transparent */
.jp-icon-hover :hover .jp-icon-none-hover[fill] {
  fill: none;
}

.jp-icon-hover :hover .jp-icon-none-hover[stroke] {
  stroke: none;
}

/**
 * inverse colors
 */

/* inverse recolor the primary elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* inverse recolor the accent elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* Sibling imports */

/* Override Blueprint's _reset.scss styles */
html {
  box-sizing: unset;
}

*,
*::before,
*::after {
  box-sizing: unset;
}

body {
  color: unset;
  font-family: var(--jp-ui-font-family);
}

p {
  margin-top: unset;
  margin-bottom: unset;
}

small {
  font-size: unset;
}

strong {
  font-weight: unset;
}

/* Override Blueprint's _typography.scss styles */
a {
  text-decoration: unset;
  color: unset;
}
a:hover {
  text-decoration: unset;
  color: unset;
}

/* Override Blueprint's _accessibility.scss styles */
:focus {
  outline: unset;
  outline-offset: unset;
  -moz-outline-radius: unset;
}

/* Styles for ui-components */
.jp-Button {
  border-radius: var(--jp-border-radius);
  padding: 0px 12px;
  font-size: var(--jp-ui-font-size1);
}

/* Use our own theme for hover styles */
button.jp-Button.bp3-button.bp3-minimal:hover {
  background-color: var(--jp-layout-color2);
}
.jp-Button.minimal {
  color: unset !important;
}

.jp-Button.jp-ToolbarButtonComponent {
  text-transform: none;
}

.jp-InputGroup input {
  box-sizing: border-box;
  border-radius: 0;
  background-color: transparent;
  color: var(--jp-ui-font-color0);
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
}

.jp-InputGroup input:focus {
  box-shadow: inset 0 0 0 var(--jp-border-width)
      var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.jp-InputGroup input::placeholder,
input::placeholder {
  color: var(--jp-ui-font-color3);
}

.jp-BPIcon {
  display: inline-block;
  vertical-align: middle;
  margin: auto;
}

/* Stop blueprint futzing with our icon fills */
.bp3-icon.jp-BPIcon > svg:not([fill]) {
  fill: var(--jp-inverse-layout-color3);
}

.jp-InputGroupAction {
  padding: 6px;
}

.jp-HTMLSelect.jp-DefaultStyle select {
  background-color: initial;
  border: none;
  border-radius: 0;
  box-shadow: none;
  color: var(--jp-ui-font-color0);
  display: block;
  font-size: var(--jp-ui-font-size1);
  height: 24px;
  line-height: 14px;
  padding: 0 25px 0 10px;
  text-align: left;
  -moz-appearance: none;
  -webkit-appearance: none;
}

/* Use our own theme for hover and option styles */
.jp-HTMLSelect.jp-DefaultStyle select:hover,
.jp-HTMLSelect.jp-DefaultStyle select > option {
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color0);
}
select {
  box-sizing: border-box;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapse {
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-top: 1px solid var(--jp-border-color2);
  border-bottom: 1px solid var(--jp-border-color2);
}

.jp-Collapse-header {
  padding: 1px 12px;
  color: var(--jp-ui-font-color1);
  background-color: var(--jp-layout-color1);
  font-size: var(--jp-ui-font-size2);
}

.jp-Collapse-header:hover {
  background-color: var(--jp-layout-color2);
}

.jp-Collapse-contents {
  padding: 0px 12px 0px 12px;
  background-color: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  overflow: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-commandpalette-search-height: 28px;
}

/*-----------------------------------------------------------------------------
| Overall styles
|----------------------------------------------------------------------------*/

.lm-CommandPalette {
  padding-bottom: 0px;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Search
|----------------------------------------------------------------------------*/

.lm-CommandPalette-search {
  padding: 4px;
  background-color: var(--jp-layout-color1);
  z-index: 2;
}

.lm-CommandPalette-wrapper {
  overflow: overlay;
  padding: 0px 9px;
  background-color: var(--jp-input-active-background);
  height: 30px;
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
}

.lm-CommandPalette.lm-mod-focused .lm-CommandPalette-wrapper {
  box-shadow: inset 0 0 0 1px var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.lm-CommandPalette-wrapper::after {
  content: ' ';
  color: white;
  background-color: var(--jp-brand-color1);
  position: absolute;
  top: 4px;
  right: 4px;
  height: 30px;
  width: 10px;
  padding: 0px 10px;
  background-image: var(--jp-icon-search-white);
  background-size: 20px;
  background-repeat: no-repeat;
  background-position: center;
}

.lm-CommandPalette-input {
  background: transparent;
  width: calc(100% - 18px);
  float: left;
  border: none;
  outline: none;
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  line-height: var(--jp-private-commandpalette-search-height);
}

.lm-CommandPalette-input::-webkit-input-placeholder,
.lm-CommandPalette-input::-moz-placeholder,
.lm-CommandPalette-input:-ms-input-placeholder {
  color: var(--jp-ui-font-color3);
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Results
|----------------------------------------------------------------------------*/

.lm-CommandPalette-header:first-child {
  margin-top: 0px;
}

.lm-CommandPalette-header {
  border-bottom: solid var(--jp-border-width) var(--jp-border-color2);
  color: var(--jp-ui-font-color1);
  cursor: pointer;
  display: flex;
  font-size: var(--jp-ui-font-size0);
  font-weight: 600;
  letter-spacing: 1px;
  margin-top: 8px;
  padding: 8px 0 8px 12px;
  text-transform: uppercase;
}

.lm-CommandPalette-header.lm-mod-active {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-header > mark {
  background-color: transparent;
  font-weight: bold;
  color: var(--jp-ui-font-color1);
}

.lm-CommandPalette-item {
  padding: 4px 12px 4px 4px;
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  font-weight: 400;
  display: flex;
}

.lm-CommandPalette-item.lm-mod-disabled {
  color: var(--jp-ui-font-color3);
}

.lm-CommandPalette-item.lm-mod-active {
  background: var(--jp-layout-color3);
}

.lm-CommandPalette-item.lm-mod-active:hover:not(.lm-mod-disabled) {
  background: var(--jp-layout-color4);
}

.lm-CommandPalette-item:hover:not(.lm-mod-active):not(.lm-mod-disabled) {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-itemContent {
  overflow: hidden;
}

.lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-font-color0);
  background-color: transparent;
  font-weight: bold;
}

.lm-CommandPalette-item.lm-mod-disabled mark {
  color: var(--jp-ui-font-color3);
}

.lm-CommandPalette-item .lm-CommandPalette-itemIcon {
  margin: 0 4px 0 0;
  position: relative;
  width: 16px;
  top: 2px;
  flex: 0 0 auto;
}

.lm-CommandPalette-item.lm-mod-disabled .lm-CommandPalette-itemIcon {
  opacity: 0.4;
}

.lm-CommandPalette-item .lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}

.lm-CommandPalette-itemCaption {
  display: none;
}

.lm-CommandPalette-content {
  background-color: var(--jp-layout-color1);
}

.lm-CommandPalette-content:empty:after {
  content: 'No results';
  margin: auto;
  margin-top: 20px;
  width: 100px;
  display: block;
  font-size: var(--jp-ui-font-size2);
  font-family: var(--jp-ui-font-family);
  font-weight: lighter;
}

.lm-CommandPalette-emptyMessage {
  text-align: center;
  margin-top: 24px;
  line-height: 1.32;
  padding: 0px 8px;
  color: var(--jp-content-font-color3);
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Dialog {
  position: absolute;
  z-index: 10000;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  top: 0px;
  left: 0px;
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-dialog-background);
}

.jp-Dialog-content {
  display: flex;
  flex-direction: column;
  margin-left: auto;
  margin-right: auto;
  background: var(--jp-layout-color1);
  padding: 24px;
  padding-bottom: 12px;
  min-width: 300px;
  min-height: 150px;
  max-width: 1000px;
  max-height: 500px;
  box-sizing: border-box;
  box-shadow: var(--jp-elevation-z20);
  word-wrap: break-word;
  border-radius: var(--jp-border-radius);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color1);
}

.jp-Dialog-button {
  overflow: visible;
}

button.jp-Dialog-button:focus {
  outline: 1px solid var(--jp-brand-color1);
  outline-offset: 4px;
  -moz-outline-radius: 0px;
}

button.jp-Dialog-button:focus::-moz-focus-inner {
  border: 0;
}

.jp-Dialog-header {
  flex: 0 0 auto;
  padding-bottom: 12px;
  font-size: var(--jp-ui-font-size3);
  font-weight: 400;
  color: var(--jp-ui-font-color0);
}

.jp-Dialog-body {
  display: flex;
  flex-direction: column;
  flex: 1 1 auto;
  font-size: var(--jp-ui-font-size1);
  background: var(--jp-layout-color1);
  overflow: auto;
}

.jp-Dialog-footer {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  flex: 0 0 auto;
  margin-left: -12px;
  margin-right: -12px;
  padding: 12px;
}

.jp-Dialog-title {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.jp-Dialog-body > .jp-select-wrapper {
  width: 100%;
}

.jp-Dialog-body > button {
  padding: 0px 16px;
}

.jp-Dialog-body > label {
  line-height: 1.4;
  color: var(--jp-ui-font-color0);
}

.jp-Dialog-button.jp-mod-styled:not(:last-child) {
  margin-right: 12px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-HoverBox {
  position: fixed;
}

.jp-HoverBox.jp-mod-outofview {
  display: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-IFrame {
  width: 100%;
  height: 100%;
}

.jp-IFrame > iframe {
  border: none;
}

/*
When drag events occur, `p-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-IFrame {
  position: relative;
}

body.lm-mod-override-cursor .jp-IFrame:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MainAreaWidget > :focus {
  outline: none;
}

/**
 * google-material-color v1.2.6
 * https://github.com/danlevan/google-material-color
 */
:root {
  --md-red-50: #ffebee;
  --md-red-100: #ffcdd2;
  --md-red-200: #ef9a9a;
  --md-red-300: #e57373;
  --md-red-400: #ef5350;
  --md-red-500: #f44336;
  --md-red-600: #e53935;
  --md-red-700: #d32f2f;
  --md-red-800: #c62828;
  --md-red-900: #b71c1c;
  --md-red-A100: #ff8a80;
  --md-red-A200: #ff5252;
  --md-red-A400: #ff1744;
  --md-red-A700: #d50000;

  --md-pink-50: #fce4ec;
  --md-pink-100: #f8bbd0;
  --md-pink-200: #f48fb1;
  --md-pink-300: #f06292;
  --md-pink-400: #ec407a;
  --md-pink-500: #e91e63;
  --md-pink-600: #d81b60;
  --md-pink-700: #c2185b;
  --md-pink-800: #ad1457;
  --md-pink-900: #880e4f;
  --md-pink-A100: #ff80ab;
  --md-pink-A200: #ff4081;
  --md-pink-A400: #f50057;
  --md-pink-A700: #c51162;

  --md-purple-50: #f3e5f5;
  --md-purple-100: #e1bee7;
  --md-purple-200: #ce93d8;
  --md-purple-300: #ba68c8;
  --md-purple-400: #ab47bc;
  --md-purple-500: #9c27b0;
  --md-purple-600: #8e24aa;
  --md-purple-700: #7b1fa2;
  --md-purple-800: #6a1b9a;
  --md-purple-900: #4a148c;
  --md-purple-A100: #ea80fc;
  --md-purple-A200: #e040fb;
  --md-purple-A400: #d500f9;
  --md-purple-A700: #aa00ff;

  --md-deep-purple-50: #ede7f6;
  --md-deep-purple-100: #d1c4e9;
  --md-deep-purple-200: #b39ddb;
  --md-deep-purple-300: #9575cd;
  --md-deep-purple-400: #7e57c2;
  --md-deep-purple-500: #673ab7;
  --md-deep-purple-600: #5e35b1;
  --md-deep-purple-700: #512da8;
  --md-deep-purple-800: #4527a0;
  --md-deep-purple-900: #311b92;
  --md-deep-purple-A100: #b388ff;
  --md-deep-purple-A200: #7c4dff;
  --md-deep-purple-A400: #651fff;
  --md-deep-purple-A700: #6200ea;

  --md-indigo-50: #e8eaf6;
  --md-indigo-100: #c5cae9;
  --md-indigo-200: #9fa8da;
  --md-indigo-300: #7986cb;
  --md-indigo-400: #5c6bc0;
  --md-indigo-500: #3f51b5;
  --md-indigo-600: #3949ab;
  --md-indigo-700: #303f9f;
  --md-indigo-800: #283593;
  --md-indigo-900: #1a237e;
  --md-indigo-A100: #8c9eff;
  --md-indigo-A200: #536dfe;
  --md-indigo-A400: #3d5afe;
  --md-indigo-A700: #304ffe;

  --md-blue-50: #e3f2fd;
  --md-blue-100: #bbdefb;
  --md-blue-200: #90caf9;
  --md-blue-300: #64b5f6;
  --md-blue-400: #42a5f5;
  --md-blue-500: #2196f3;
  --md-blue-600: #1e88e5;
  --md-blue-700: #1976d2;
  --md-blue-800: #1565c0;
  --md-blue-900: #0d47a1;
  --md-blue-A100: #82b1ff;
  --md-blue-A200: #448aff;
  --md-blue-A400: #2979ff;
  --md-blue-A700: #2962ff;

  --md-light-blue-50: #e1f5fe;
  --md-light-blue-100: #b3e5fc;
  --md-light-blue-200: #81d4fa;
  --md-light-blue-300: #4fc3f7;
  --md-light-blue-400: #29b6f6;
  --md-light-blue-500: #03a9f4;
  --md-light-blue-600: #039be5;
  --md-light-blue-700: #0288d1;
  --md-light-blue-800: #0277bd;
  --md-light-blue-900: #01579b;
  --md-light-blue-A100: #80d8ff;
  --md-light-blue-A200: #40c4ff;
  --md-light-blue-A400: #00b0ff;
  --md-light-blue-A700: #0091ea;

  --md-cyan-50: #e0f7fa;
  --md-cyan-100: #b2ebf2;
  --md-cyan-200: #80deea;
  --md-cyan-300: #4dd0e1;
  --md-cyan-400: #26c6da;
  --md-cyan-500: #00bcd4;
  --md-cyan-600: #00acc1;
  --md-cyan-700: #0097a7;
  --md-cyan-800: #00838f;
  --md-cyan-900: #006064;
  --md-cyan-A100: #84ffff;
  --md-cyan-A200: #18ffff;
  --md-cyan-A400: #00e5ff;
  --md-cyan-A700: #00b8d4;

  --md-teal-50: #e0f2f1;
  --md-teal-100: #b2dfdb;
  --md-teal-200: #80cbc4;
  --md-teal-300: #4db6ac;
  --md-teal-400: #26a69a;
  --md-teal-500: #009688;
  --md-teal-600: #00897b;
  --md-teal-700: #00796b;
  --md-teal-800: #00695c;
  --md-teal-900: #004d40;
  --md-teal-A100: #a7ffeb;
  --md-teal-A200: #64ffda;
  --md-teal-A400: #1de9b6;
  --md-teal-A700: #00bfa5;

  --md-green-50: #e8f5e9;
  --md-green-100: #c8e6c9;
  --md-green-200: #a5d6a7;
  --md-green-300: #81c784;
  --md-green-400: #66bb6a;
  --md-green-500: #4caf50;
  --md-green-600: #43a047;
  --md-green-700: #388e3c;
  --md-green-800: #2e7d32;
  --md-green-900: #1b5e20;
  --md-green-A100: #b9f6ca;
  --md-green-A200: #69f0ae;
  --md-green-A400: #00e676;
  --md-green-A700: #00c853;

  --md-light-green-50: #f1f8e9;
  --md-light-green-100: #dcedc8;
  --md-light-green-200: #c5e1a5;
  --md-light-green-300: #aed581;
  --md-light-green-400: #9ccc65;
  --md-light-green-500: #8bc34a;
  --md-light-green-600: #7cb342;
  --md-light-green-700: #689f38;
  --md-light-green-800: #558b2f;
  --md-light-green-900: #33691e;
  --md-light-green-A100: #ccff90;
  --md-light-green-A200: #b2ff59;
  --md-light-green-A400: #76ff03;
  --md-light-green-A700: #64dd17;

  --md-lime-50: #f9fbe7;
  --md-lime-100: #f0f4c3;
  --md-lime-200: #e6ee9c;
  --md-lime-300: #dce775;
  --md-lime-400: #d4e157;
  --md-lime-500: #cddc39;
  --md-lime-600: #c0ca33;
  --md-lime-700: #afb42b;
  --md-lime-800: #9e9d24;
  --md-lime-900: #827717;
  --md-lime-A100: #f4ff81;
  --md-lime-A200: #eeff41;
  --md-lime-A400: #c6ff00;
  --md-lime-A700: #aeea00;

  --md-yellow-50: #fffde7;
  --md-yellow-100: #fff9c4;
  --md-yellow-200: #fff59d;
  --md-yellow-300: #fff176;
  --md-yellow-400: #ffee58;
  --md-yellow-500: #ffeb3b;
  --md-yellow-600: #fdd835;
  --md-yellow-700: #fbc02d;
  --md-yellow-800: #f9a825;
  --md-yellow-900: #f57f17;
  --md-yellow-A100: #ffff8d;
  --md-yellow-A200: #ffff00;
  --md-yellow-A400: #ffea00;
  --md-yellow-A700: #ffd600;

  --md-amber-50: #fff8e1;
  --md-amber-100: #ffecb3;
  --md-amber-200: #ffe082;
  --md-amber-300: #ffd54f;
  --md-amber-400: #ffca28;
  --md-amber-500: #ffc107;
  --md-amber-600: #ffb300;
  --md-amber-700: #ffa000;
  --md-amber-800: #ff8f00;
  --md-amber-900: #ff6f00;
  --md-amber-A100: #ffe57f;
  --md-amber-A200: #ffd740;
  --md-amber-A400: #ffc400;
  --md-amber-A700: #ffab00;

  --md-orange-50: #fff3e0;
  --md-orange-100: #ffe0b2;
  --md-orange-200: #ffcc80;
  --md-orange-300: #ffb74d;
  --md-orange-400: #ffa726;
  --md-orange-500: #ff9800;
  --md-orange-600: #fb8c00;
  --md-orange-700: #f57c00;
  --md-orange-800: #ef6c00;
  --md-orange-900: #e65100;
  --md-orange-A100: #ffd180;
  --md-orange-A200: #ffab40;
  --md-orange-A400: #ff9100;
  --md-orange-A700: #ff6d00;

  --md-deep-orange-50: #fbe9e7;
  --md-deep-orange-100: #ffccbc;
  --md-deep-orange-200: #ffab91;
  --md-deep-orange-300: #ff8a65;
  --md-deep-orange-400: #ff7043;
  --md-deep-orange-500: #ff5722;
  --md-deep-orange-600: #f4511e;
  --md-deep-orange-700: #e64a19;
  --md-deep-orange-800: #d84315;
  --md-deep-orange-900: #bf360c;
  --md-deep-orange-A100: #ff9e80;
  --md-deep-orange-A200: #ff6e40;
  --md-deep-orange-A400: #ff3d00;
  --md-deep-orange-A700: #dd2c00;

  --md-brown-50: #efebe9;
  --md-brown-100: #d7ccc8;
  --md-brown-200: #bcaaa4;
  --md-brown-300: #a1887f;
  --md-brown-400: #8d6e63;
  --md-brown-500: #795548;
  --md-brown-600: #6d4c41;
  --md-brown-700: #5d4037;
  --md-brown-800: #4e342e;
  --md-brown-900: #3e2723;

  --md-grey-50: #fafafa;
  --md-grey-100: #f5f5f5;
  --md-grey-200: #eeeeee;
  --md-grey-300: #e0e0e0;
  --md-grey-400: #bdbdbd;
  --md-grey-500: #9e9e9e;
  --md-grey-600: #757575;
  --md-grey-700: #616161;
  --md-grey-800: #424242;
  --md-grey-900: #212121;

  --md-blue-grey-50: #eceff1;
  --md-blue-grey-100: #cfd8dc;
  --md-blue-grey-200: #b0bec5;
  --md-blue-grey-300: #90a4ae;
  --md-blue-grey-400: #78909c;
  --md-blue-grey-500: #607d8b;
  --md-blue-grey-600: #546e7a;
  --md-blue-grey-700: #455a64;
  --md-blue-grey-800: #37474f;
  --md-blue-grey-900: #263238;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Spinner {
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 10;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-layout-color0);
  outline: none;
}

.jp-SpinnerContent {
  font-size: 10px;
  margin: 50px auto;
  text-indent: -9999em;
  width: 3em;
  height: 3em;
  border-radius: 50%;
  background: var(--jp-brand-color3);
  background: linear-gradient(
    to right,
    #f37626 10%,
    rgba(255, 255, 255, 0) 42%
  );
  position: relative;
  animation: load3 1s infinite linear, fadeIn 1s;
}

.jp-SpinnerContent:before {
  width: 50%;
  height: 50%;
  background: #f37626;
  border-radius: 100% 0 0 0;
  position: absolute;
  top: 0;
  left: 0;
  content: '';
}

.jp-SpinnerContent:after {
  background: var(--jp-layout-color0);
  width: 75%;
  height: 75%;
  border-radius: 50%;
  content: '';
  margin: auto;
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@keyframes load3 {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

button.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: none;
  box-sizing: border-box;
  text-align: center;
  line-height: 32px;
  height: 32px;
  padding: 0px 12px;
  letter-spacing: 0.8px;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input.jp-mod-styled {
  background: var(--jp-input-background);
  height: 28px;
  box-sizing: border-box;
  border: var(--jp-border-width) solid var(--jp-border-color1);
  padding-left: 7px;
  padding-right: 7px;
  font-size: var(--jp-ui-font-size2);
  color: var(--jp-ui-font-color0);
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input.jp-mod-styled:focus {
  border: var(--jp-border-width) solid var(--md-blue-500);
  box-shadow: inset 0 0 4px var(--md-blue-300);
}

.jp-select-wrapper {
  display: flex;
  position: relative;
  flex-direction: column;
  padding: 1px;
  background-color: var(--jp-layout-color1);
  height: 28px;
  box-sizing: border-box;
  margin-bottom: 12px;
}

.jp-select-wrapper.jp-mod-focused select.jp-mod-styled {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-input-active-background);
}

select.jp-mod-styled:hover {
  background-color: var(--jp-layout-color1);
  cursor: pointer;
  color: var(--jp-ui-font-color0);
  background-color: var(--jp-input-hover-background);
  box-shadow: inset 0 0px 1px rgba(0, 0, 0, 0.5);
}

select.jp-mod-styled {
  flex: 1 1 auto;
  height: 32px;
  width: 100%;
  font-size: var(--jp-ui-font-size2);
  background: var(--jp-input-background);
  color: var(--jp-ui-font-color0);
  padding: 0 25px 0 8px;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0px;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

:root {
  --jp-private-toolbar-height: calc(
    28px + var(--jp-border-width)
  ); /* leave 28px for content */
}

.jp-Toolbar {
  color: var(--jp-ui-font-color1);
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  box-shadow: var(--jp-toolbar-box-shadow);
  background: var(--jp-toolbar-background);
  min-height: var(--jp-toolbar-micro-height);
  padding: 2px;
  z-index: 1;
}

/* Toolbar items */

.jp-Toolbar > .jp-Toolbar-item.jp-Toolbar-spacer {
  flex-grow: 1;
  flex-shrink: 1;
}

.jp-Toolbar-item.jp-Toolbar-kernelStatus {
  display: inline-block;
  width: 32px;
  background-repeat: no-repeat;
  background-position: center;
  background-size: 16px;
}

.jp-Toolbar > .jp-Toolbar-item {
  flex: 0 0 auto;
  display: flex;
  padding-left: 1px;
  padding-right: 1px;
  font-size: var(--jp-ui-font-size1);
  line-height: var(--jp-private-toolbar-height);
  height: 100%;
}

/* Toolbar buttons */

/* This is the div we use to wrap the react component into a Widget */
div.jp-ToolbarButton {
  color: transparent;
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0px;
  margin: 0px;
}

button.jp-ToolbarButtonComponent {
  background: var(--jp-layout-color1);
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0px 6px;
  margin: 0px;
  height: 24px;
  border-radius: var(--jp-border-radius);
  display: flex;
  align-items: center;
  text-align: center;
  font-size: 14px;
  min-width: unset;
  min-height: unset;
}

button.jp-ToolbarButtonComponent:disabled {
  opacity: 0.4;
}

button.jp-ToolbarButtonComponent span {
  padding: 0px;
  flex: 0 0 auto;
}

button.jp-ToolbarButtonComponent .jp-ToolbarButtonComponent-label {
  font-size: var(--jp-ui-font-size1);
  line-height: 100%;
  padding-left: 2px;
  color: var(--jp-ui-font-color1);
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ body.p-mod-override-cursor *, /* </DEPRECATED> */
body.lm-mod-override-cursor * {
  cursor: inherit !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-JSONEditor {
  display: flex;
  flex-direction: column;
  width: 100%;
}

.jp-JSONEditor-host {
  flex: 1 1 auto;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0px;
  background: var(--jp-layout-color0);
  min-height: 50px;
  padding: 1px;
}

.jp-JSONEditor.jp-mod-error .jp-JSONEditor-host {
  border-color: red;
  outline-color: red;
}

.jp-JSONEditor-header {
  display: flex;
  flex: 1 0 auto;
  padding: 0 0 0 12px;
}

.jp-JSONEditor-header label {
  flex: 0 0 auto;
}

.jp-JSONEditor-commitButton {
  height: 16px;
  width: 16px;
  background-size: 18px;
  background-repeat: no-repeat;
  background-position: center;
}

.jp-JSONEditor-host.jp-mod-focused {
  background-color: var(--jp-input-active-background);
  border: 1px solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

.jp-Editor.jp-mod-dropTarget {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* BASICS */

.CodeMirror {
  /* Set height, width, borders, and global font properties here */
  font-family: monospace;
  height: 300px;
  color: black;
  direction: ltr;
}

/* PADDING */

.CodeMirror-lines {
  padding: 4px 0; /* Vertical padding around content */
}
.CodeMirror pre.CodeMirror-line,
.CodeMirror pre.CodeMirror-line-like {
  padding: 0 4px; /* Horizontal padding of content */
}

.CodeMirror-scrollbar-filler, .CodeMirror-gutter-filler {
  background-color: white; /* The little square between H and V scrollbars */
}

/* GUTTER */

.CodeMirror-gutters {
  border-right: 1px solid #ddd;
  background-color: #f7f7f7;
  white-space: nowrap;
}
.CodeMirror-linenumbers {}
.CodeMirror-linenumber {
  padding: 0 3px 0 5px;
  min-width: 20px;
  text-align: right;
  color: #999;
  white-space: nowrap;
}

.CodeMirror-guttermarker { color: black; }
.CodeMirror-guttermarker-subtle { color: #999; }

/* CURSOR */

.CodeMirror-cursor {
  border-left: 1px solid black;
  border-right: none;
  width: 0;
}
/* Shown when moving in bi-directional text */
.CodeMirror div.CodeMirror-secondarycursor {
  border-left: 1px solid silver;
}
.cm-fat-cursor .CodeMirror-cursor {
  width: auto;
  border: 0 !important;
  background: #7e7;
}
.cm-fat-cursor div.CodeMirror-cursors {
  z-index: 1;
}
.cm-fat-cursor-mark {
  background-color: rgba(20, 255, 20, 0.5);
  -webkit-animation: blink 1.06s steps(1) infinite;
  -moz-animation: blink 1.06s steps(1) infinite;
  animation: blink 1.06s steps(1) infinite;
}
.cm-animate-fat-cursor {
  width: auto;
  border: 0;
  -webkit-animation: blink 1.06s steps(1) infinite;
  -moz-animation: blink 1.06s steps(1) infinite;
  animation: blink 1.06s steps(1) infinite;
  background-color: #7e7;
}
@-moz-keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}
@-webkit-keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}
@keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}

/* Can style cursor different in overwrite (non-insert) mode */
.CodeMirror-overwrite .CodeMirror-cursor {}

.cm-tab { display: inline-block; text-decoration: inherit; }

.CodeMirror-rulers {
  position: absolute;
  left: 0; right: 0; top: -50px; bottom: 0;
  overflow: hidden;
}
.CodeMirror-ruler {
  border-left: 1px solid #ccc;
  top: 0; bottom: 0;
  position: absolute;
}

/* DEFAULT THEME */

.cm-s-default .cm-header {color: blue;}
.cm-s-default .cm-quote {color: #090;}
.cm-negative {color: #d44;}
.cm-positive {color: #292;}
.cm-header, .cm-strong {font-weight: bold;}
.cm-em {font-style: italic;}
.cm-link {text-decoration: underline;}
.cm-strikethrough {text-decoration: line-through;}

.cm-s-default .cm-keyword {color: #708;}
.cm-s-default .cm-atom {color: #219;}
.cm-s-default .cm-number {color: #164;}
.cm-s-default .cm-def {color: #00f;}
.cm-s-default .cm-variable,
.cm-s-default .cm-punctuation,
.cm-s-default .cm-property,
.cm-s-default .cm-operator {}
.cm-s-default .cm-variable-2 {color: #05a;}
.cm-s-default .cm-variable-3, .cm-s-default .cm-type {color: #085;}
.cm-s-default .cm-comment {color: #a50;}
.cm-s-default .cm-string {color: #a11;}
.cm-s-default .cm-string-2 {color: #f50;}
.cm-s-default .cm-meta {color: #555;}
.cm-s-default .cm-qualifier {color: #555;}
.cm-s-default .cm-builtin {color: #30a;}
.cm-s-default .cm-bracket {color: #997;}
.cm-s-default .cm-tag {color: #170;}
.cm-s-default .cm-attribute {color: #00c;}
.cm-s-default .cm-hr {color: #999;}
.cm-s-default .cm-link {color: #00c;}

.cm-s-default .cm-error {color: #f00;}
.cm-invalidchar {color: #f00;}

.CodeMirror-composing { border-bottom: 2px solid; }

/* Default styles for common addons */

div.CodeMirror span.CodeMirror-matchingbracket {color: #0b0;}
div.CodeMirror span.CodeMirror-nonmatchingbracket {color: #a22;}
.CodeMirror-matchingtag { background: rgba(255, 150, 0, .3); }
.CodeMirror-activeline-background {background: #e8f2ff;}

/* STOP */

/* The rest of this file contains styles related to the mechanics of
   the editor. You probably shouldn't touch them. */

.CodeMirror {
  position: relative;
  overflow: hidden;
  background: white;
}

.CodeMirror-scroll {
  overflow: scroll !important; /* Things will break if this is overridden */
  /* 30px is the magic margin used to hide the element's real scrollbars */
  /* See overflow: hidden in .CodeMirror */
  margin-bottom: -30px; margin-right: -30px;
  padding-bottom: 30px;
  height: 100%;
  outline: none; /* Prevent dragging from highlighting the element */
  position: relative;
}
.CodeMirror-sizer {
  position: relative;
  border-right: 30px solid transparent;
}

/* The fake, visible scrollbars. Used to force redraw during scrolling
   before actual scrolling happens, thus preventing shaking and
   flickering artifacts. */
.CodeMirror-vscrollbar, .CodeMirror-hscrollbar, .CodeMirror-scrollbar-filler, .CodeMirror-gutter-filler {
  position: absolute;
  z-index: 6;
  display: none;
}
.CodeMirror-vscrollbar {
  right: 0; top: 0;
  overflow-x: hidden;
  overflow-y: scroll;
}
.CodeMirror-hscrollbar {
  bottom: 0; left: 0;
  overflow-y: hidden;
  overflow-x: scroll;
}
.CodeMirror-scrollbar-filler {
  right: 0; bottom: 0;
}
.CodeMirror-gutter-filler {
  left: 0; bottom: 0;
}

.CodeMirror-gutters {
  position: absolute; left: 0; top: 0;
  min-height: 100%;
  z-index: 3;
}
.CodeMirror-gutter {
  white-space: normal;
  height: 100%;
  display: inline-block;
  vertical-align: top;
  margin-bottom: -30px;
}
.CodeMirror-gutter-wrapper {
  position: absolute;
  z-index: 4;
  background: none !important;
  border: none !important;
}
.CodeMirror-gutter-background {
  position: absolute;
  top: 0; bottom: 0;
  z-index: 4;
}
.CodeMirror-gutter-elt {
  position: absolute;
  cursor: default;
  z-index: 4;
}
.CodeMirror-gutter-wrapper ::selection { background-color: transparent }
.CodeMirror-gutter-wrapper ::-moz-selection { background-color: transparent }

.CodeMirror-lines {
  cursor: text;
  min-height: 1px; /* prevents collapsing before first draw */
}
.CodeMirror pre.CodeMirror-line,
.CodeMirror pre.CodeMirror-line-like {
  /* Reset some styles that the rest of the page might have set */
  -moz-border-radius: 0; -webkit-border-radius: 0; border-radius: 0;
  border-width: 0;
  background: transparent;
  font-family: inherit;
  font-size: inherit;
  margin: 0;
  white-space: pre;
  word-wrap: normal;
  line-height: inherit;
  color: inherit;
  z-index: 2;
  position: relative;
  overflow: visible;
  -webkit-tap-highlight-color: transparent;
  -webkit-font-variant-ligatures: contextual;
  font-variant-ligatures: contextual;
}
.CodeMirror-wrap pre.CodeMirror-line,
.CodeMirror-wrap pre.CodeMirror-line-like {
  word-wrap: break-word;
  white-space: pre-wrap;
  word-break: normal;
}

.CodeMirror-linebackground {
  position: absolute;
  left: 0; right: 0; top: 0; bottom: 0;
  z-index: 0;
}

.CodeMirror-linewidget {
  position: relative;
  z-index: 2;
  padding: 0.1px; /* Force widget margins to stay inside of the container */
}

.CodeMirror-widget {}

.CodeMirror-rtl pre { direction: rtl; }

.CodeMirror-code {
  outline: none;
}

/* Force content-box sizing for the elements where we expect it */
.CodeMirror-scroll,
.CodeMirror-sizer,
.CodeMirror-gutter,
.CodeMirror-gutters,
.CodeMirror-linenumber {
  -moz-box-sizing: content-box;
  box-sizing: content-box;
}

.CodeMirror-measure {
  position: absolute;
  width: 100%;
  height: 0;
  overflow: hidden;
  visibility: hidden;
}

.CodeMirror-cursor {
  position: absolute;
  pointer-events: none;
}
.CodeMirror-measure pre { position: static; }

div.CodeMirror-cursors {
  visibility: hidden;
  position: relative;
  z-index: 3;
}
div.CodeMirror-dragcursors {
  visibility: visible;
}

.CodeMirror-focused div.CodeMirror-cursors {
  visibility: visible;
}

.CodeMirror-selected { background: #d9d9d9; }
.CodeMirror-focused .CodeMirror-selected { background: #d7d4f0; }
.CodeMirror-crosshair { cursor: crosshair; }
.CodeMirror-line::selection, .CodeMirror-line > span::selection, .CodeMirror-line > span > span::selection { background: #d7d4f0; }
.CodeMirror-line::-moz-selection, .CodeMirror-line > span::-moz-selection, .CodeMirror-line > span > span::-moz-selection { background: #d7d4f0; }

.cm-searching {
  background-color: #ffa;
  background-color: rgba(255, 255, 0, .4);
}

/* Used to force a border model for a node */
.cm-force-border { padding-right: .1px; }

@media print {
  /* Hide the cursor when printing */
  .CodeMirror div.CodeMirror-cursors {
    visibility: hidden;
  }
}

/* See issue #2901 */
.cm-tab-wrap-hack:after { content: ''; }

/* Help users use markselection to safely style text background */
span.CodeMirror-selectedtext { background: none; }

.CodeMirror-dialog {
  position: absolute;
  left: 0; right: 0;
  background: inherit;
  z-index: 15;
  padding: .1em .8em;
  overflow: hidden;
  color: inherit;
}

.CodeMirror-dialog-top {
  border-bottom: 1px solid #eee;
  top: 0;
}

.CodeMirror-dialog-bottom {
  border-top: 1px solid #eee;
  bottom: 0;
}

.CodeMirror-dialog input {
  border: none;
  outline: none;
  background: transparent;
  width: 20em;
  color: inherit;
  font-family: monospace;
}

.CodeMirror-dialog button {
  font-size: 70%;
}

.CodeMirror-foldmarker {
  color: blue;
  text-shadow: #b9f 1px 1px 2px, #b9f -1px -1px 2px, #b9f 1px -1px 2px, #b9f -1px 1px 2px;
  font-family: arial;
  line-height: .3;
  cursor: pointer;
}
.CodeMirror-foldgutter {
  width: .7em;
}
.CodeMirror-foldgutter-open,
.CodeMirror-foldgutter-folded {
  cursor: pointer;
}
.CodeMirror-foldgutter-open:after {
  content: "\25BE";
}
.CodeMirror-foldgutter-folded:after {
  content: "\25B8";
}

/*
  Name:       material
  Author:     Mattia Astorino (http://github.com/equinusocio)
  Website:    https://material-theme.site/
*/

.cm-s-material.CodeMirror {
  background-color: #263238;
  color: #EEFFFF;
}

.cm-s-material .CodeMirror-gutters {
  background: #263238;
  color: #546E7A;
  border: none;
}

.cm-s-material .CodeMirror-guttermarker,
.cm-s-material .CodeMirror-guttermarker-subtle,
.cm-s-material .CodeMirror-linenumber {
  color: #546E7A;
}

.cm-s-material .CodeMirror-cursor {
  border-left: 1px solid #FFCC00;
}

.cm-s-material div.CodeMirror-selected {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material.CodeMirror-focused div.CodeMirror-selected {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material .CodeMirror-line::selection,
.cm-s-material .CodeMirror-line>span::selection,
.cm-s-material .CodeMirror-line>span>span::selection {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material .CodeMirror-line::-moz-selection,
.cm-s-material .CodeMirror-line>span::-moz-selection,
.cm-s-material .CodeMirror-line>span>span::-moz-selection {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material .CodeMirror-activeline-background {
  background: rgba(0, 0, 0, 0.5);
}

.cm-s-material .cm-keyword {
  color: #C792EA;
}

.cm-s-material .cm-operator {
  color: #89DDFF;
}

.cm-s-material .cm-variable-2 {
  color: #EEFFFF;
}

.cm-s-material .cm-variable-3,
.cm-s-material .cm-type {
  color: #f07178;
}

.cm-s-material .cm-builtin {
  color: #FFCB6B;
}

.cm-s-material .cm-atom {
  color: #F78C6C;
}

.cm-s-material .cm-number {
  color: #FF5370;
}

.cm-s-material .cm-def {
  color: #82AAFF;
}

.cm-s-material .cm-string {
  color: #C3E88D;
}

.cm-s-material .cm-string-2 {
  color: #f07178;
}

.cm-s-material .cm-comment {
  color: #546E7A;
}

.cm-s-material .cm-variable {
  color: #f07178;
}

.cm-s-material .cm-tag {
  color: #FF5370;
}

.cm-s-material .cm-meta {
  color: #FFCB6B;
}

.cm-s-material .cm-attribute {
  color: #C792EA;
}

.cm-s-material .cm-property {
  color: #C792EA;
}

.cm-s-material .cm-qualifier {
  color: #DECB6B;
}

.cm-s-material .cm-variable-3,
.cm-s-material .cm-type {
  color: #DECB6B;
}


.cm-s-material .cm-error {
  color: rgba(255, 255, 255, 1.0);
  background-color: #FF5370;
}

.cm-s-material .CodeMirror-matchingbracket {
  text-decoration: underline;
  color: white !important;
}
/**
 * "
 *  Using Zenburn color palette from the Emacs Zenburn Theme
 *  https://github.com/bbatsov/zenburn-emacs/blob/master/zenburn-theme.el
 *
 *  Also using parts of https://github.com/xavi/coderay-lighttable-theme
 * "
 * From: https://github.com/wisenomad/zenburn-lighttable-theme/blob/master/zenburn.css
 */

.cm-s-zenburn .CodeMirror-gutters { background: #3f3f3f !important; }
.cm-s-zenburn .CodeMirror-foldgutter-open, .CodeMirror-foldgutter-folded { color: #999; }
.cm-s-zenburn .CodeMirror-cursor { border-left: 1px solid white; }
.cm-s-zenburn { background-color: #3f3f3f; color: #dcdccc; }
.cm-s-zenburn span.cm-builtin { color: #dcdccc; font-weight: bold; }
.cm-s-zenburn span.cm-comment { color: #7f9f7f; }
.cm-s-zenburn span.cm-keyword { color: #f0dfaf; font-weight: bold; }
.cm-s-zenburn span.cm-atom { color: #bfebbf; }
.cm-s-zenburn span.cm-def { color: #dcdccc; }
.cm-s-zenburn span.cm-variable { color: #dfaf8f; }
.cm-s-zenburn span.cm-variable-2 { color: #dcdccc; }
.cm-s-zenburn span.cm-string { color: #cc9393; }
.cm-s-zenburn span.cm-string-2 { color: #cc9393; }
.cm-s-zenburn span.cm-number { color: #dcdccc; }
.cm-s-zenburn span.cm-tag { color: #93e0e3; }
.cm-s-zenburn span.cm-property { color: #dfaf8f; }
.cm-s-zenburn span.cm-attribute { color: #dfaf8f; }
.cm-s-zenburn span.cm-qualifier { color: #7cb8bb; }
.cm-s-zenburn span.cm-meta { color: #f0dfaf; }
.cm-s-zenburn span.cm-header { color: #f0efd0; }
.cm-s-zenburn span.cm-operator { color: #f0efd0; }
.cm-s-zenburn span.CodeMirror-matchingbracket { box-sizing: border-box; background: transparent; border-bottom: 1px solid; }
.cm-s-zenburn span.CodeMirror-nonmatchingbracket { border-bottom: 1px solid; background: none; }
.cm-s-zenburn .CodeMirror-activeline { background: #000000; }
.cm-s-zenburn .CodeMirror-activeline-background { background: #000000; }
.cm-s-zenburn div.CodeMirror-selected { background: #545454; }
.cm-s-zenburn .CodeMirror-focused div.CodeMirror-selected { background: #4f4f4f; }

.cm-s-abcdef.CodeMirror { background: #0f0f0f; color: #defdef; }
.cm-s-abcdef div.CodeMirror-selected { background: #515151; }
.cm-s-abcdef .CodeMirror-line::selection, .cm-s-abcdef .CodeMirror-line > span::selection, .cm-s-abcdef .CodeMirror-line > span > span::selection { background: rgba(56, 56, 56, 0.99); }
.cm-s-abcdef .CodeMirror-line::-moz-selection, .cm-s-abcdef .CodeMirror-line > span::-moz-selection, .cm-s-abcdef .CodeMirror-line > span > span::-moz-selection { background: rgba(56, 56, 56, 0.99); }
.cm-s-abcdef .CodeMirror-gutters { background: #555; border-right: 2px solid #314151; }
.cm-s-abcdef .CodeMirror-guttermarker { color: #222; }
.cm-s-abcdef .CodeMirror-guttermarker-subtle { color: azure; }
.cm-s-abcdef .CodeMirror-linenumber { color: #FFFFFF; }
.cm-s-abcdef .CodeMirror-cursor { border-left: 1px solid #00FF00; }

.cm-s-abcdef span.cm-keyword { color: darkgoldenrod; font-weight: bold; }
.cm-s-abcdef span.cm-atom { color: #77F; }
.cm-s-abcdef span.cm-number { color: violet; }
.cm-s-abcdef span.cm-def { color: #fffabc; }
.cm-s-abcdef span.cm-variable { color: #abcdef; }
.cm-s-abcdef span.cm-variable-2 { color: #cacbcc; }
.cm-s-abcdef span.cm-variable-3, .cm-s-abcdef span.cm-type { color: #def; }
.cm-s-abcdef span.cm-property { color: #fedcba; }
.cm-s-abcdef span.cm-operator { color: #ff0; }
.cm-s-abcdef span.cm-comment { color: #7a7b7c; font-style: italic;}
.cm-s-abcdef span.cm-string { color: #2b4; }
.cm-s-abcdef span.cm-meta { color: #C9F; }
.cm-s-abcdef span.cm-qualifier { color: #FFF700; }
.cm-s-abcdef span.cm-builtin { color: #30aabc; }
.cm-s-abcdef span.cm-bracket { color: #8a8a8a; }
.cm-s-abcdef span.cm-tag { color: #FFDD44; }
.cm-s-abcdef span.cm-attribute { color: #DDFF00; }
.cm-s-abcdef span.cm-error { color: #FF0000; }
.cm-s-abcdef span.cm-header { color: aquamarine; font-weight: bold; }
.cm-s-abcdef span.cm-link { color: blueviolet; }

.cm-s-abcdef .CodeMirror-activeline-background { background: #314151; }

/*

    Name:       Base16 Default Light
    Author:     Chris Kempson (http://chriskempson.com)

    CodeMirror template by Jan T. Sott (https://github.com/idleberg/base16-codemirror)
    Original Base16 color scheme by Chris Kempson (https://github.com/chriskempson/base16)

*/

.cm-s-base16-light.CodeMirror { background: #f5f5f5; color: #202020; }
.cm-s-base16-light div.CodeMirror-selected { background: #e0e0e0; }
.cm-s-base16-light .CodeMirror-line::selection, .cm-s-base16-light .CodeMirror-line > span::selection, .cm-s-base16-light .CodeMirror-line > span > span::selection { background: #e0e0e0; }
.cm-s-base16-light .CodeMirror-line::-moz-selection, .cm-s-base16-light .CodeMirror-line > span::-moz-selection, .cm-s-base16-light .CodeMirror-line > span > span::-moz-selection { background: #e0e0e0; }
.cm-s-base16-light .CodeMirror-gutters { background: #f5f5f5; border-right: 0px; }
.cm-s-base16-light .CodeMirror-guttermarker { color: #ac4142; }
.cm-s-base16-light .CodeMirror-guttermarker-subtle { color: #b0b0b0; }
.cm-s-base16-light .CodeMirror-linenumber { color: #b0b0b0; }
.cm-s-base16-light .CodeMirror-cursor { border-left: 1px solid #505050; }

.cm-s-base16-light span.cm-comment { color: #8f5536; }
.cm-s-base16-light span.cm-atom { color: #aa759f; }
.cm-s-base16-light span.cm-number { color: #aa759f; }

.cm-s-base16-light span.cm-property, .cm-s-base16-light span.cm-attribute { color: #90a959; }
.cm-s-base16-light span.cm-keyword { color: #ac4142; }
.cm-s-base16-light span.cm-string { color: #f4bf75; }

.cm-s-base16-light span.cm-variable { color: #90a959; }
.cm-s-base16-light span.cm-variable-2 { color: #6a9fb5; }
.cm-s-base16-light span.cm-def { color: #d28445; }
.cm-s-base16-light span.cm-bracket { color: #202020; }
.cm-s-base16-light span.cm-tag { color: #ac4142; }
.cm-s-base16-light span.cm-link { color: #aa759f; }
.cm-s-base16-light span.cm-error { background: #ac4142; color: #505050; }

.cm-s-base16-light .CodeMirror-activeline-background { background: #DDDCDC; }
.cm-s-base16-light .CodeMirror-matchingbracket { color: #f5f5f5 !important; background-color: #6A9FB5 !important}

/*

    Name:       Base16 Default Dark
    Author:     Chris Kempson (http://chriskempson.com)

    CodeMirror template by Jan T. Sott (https://github.com/idleberg/base16-codemirror)
    Original Base16 color scheme by Chris Kempson (https://github.com/chriskempson/base16)

*/

.cm-s-base16-dark.CodeMirror { background: #151515; color: #e0e0e0; }
.cm-s-base16-dark div.CodeMirror-selected { background: #303030; }
.cm-s-base16-dark .CodeMirror-line::selection, .cm-s-base16-dark .CodeMirror-line > span::selection, .cm-s-base16-dark .CodeMirror-line > span > span::selection { background: rgba(48, 48, 48, .99); }
.cm-s-base16-dark .CodeMirror-line::-moz-selection, .cm-s-base16-dark .CodeMirror-line > span::-moz-selection, .cm-s-base16-dark .CodeMirror-line > span > span::-moz-selection { background: rgba(48, 48, 48, .99); }
.cm-s-base16-dark .CodeMirror-gutters { background: #151515; border-right: 0px; }
.cm-s-base16-dark .CodeMirror-guttermarker { color: #ac4142; }
.cm-s-base16-dark .CodeMirror-guttermarker-subtle { color: #505050; }
.cm-s-base16-dark .CodeMirror-linenumber { color: #505050; }
.cm-s-base16-dark .CodeMirror-cursor { border-left: 1px solid #b0b0b0; }

.cm-s-base16-dark span.cm-comment { color: #8f5536; }
.cm-s-base16-dark span.cm-atom { color: #aa759f; }
.cm-s-base16-dark span.cm-number { color: #aa759f; }

.cm-s-base16-dark span.cm-property, .cm-s-base16-dark span.cm-attribute { color: #90a959; }
.cm-s-base16-dark span.cm-keyword { color: #ac4142; }
.cm-s-base16-dark span.cm-string { color: #f4bf75; }

.cm-s-base16-dark span.cm-variable { color: #90a959; }
.cm-s-base16-dark span.cm-variable-2 { color: #6a9fb5; }
.cm-s-base16-dark span.cm-def { color: #d28445; }
.cm-s-base16-dark span.cm-bracket { color: #e0e0e0; }
.cm-s-base16-dark span.cm-tag { color: #ac4142; }
.cm-s-base16-dark span.cm-link { color: #aa759f; }
.cm-s-base16-dark span.cm-error { background: #ac4142; color: #b0b0b0; }

.cm-s-base16-dark .CodeMirror-activeline-background { background: #202020; }
.cm-s-base16-dark .CodeMirror-matchingbracket { text-decoration: underline; color: white !important; }

/*

    Name:       dracula
    Author:     Michael Kaminsky (http://github.com/mkaminsky11)

    Original dracula color scheme by Zeno Rocha (https://github.com/zenorocha/dracula-theme)

*/


.cm-s-dracula.CodeMirror, .cm-s-dracula .CodeMirror-gutters {
  background-color: #282a36 !important;
  color: #f8f8f2 !important;
  border: none;
}
.cm-s-dracula .CodeMirror-gutters { color: #282a36; }
.cm-s-dracula .CodeMirror-cursor { border-left: solid thin #f8f8f0; }
.cm-s-dracula .CodeMirror-linenumber { color: #6D8A88; }
.cm-s-dracula .CodeMirror-selected { background: rgba(255, 255, 255, 0.10); }
.cm-s-dracula .CodeMirror-line::selection, .cm-s-dracula .CodeMirror-line > span::selection, .cm-s-dracula .CodeMirror-line > span > span::selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-dracula .CodeMirror-line::-moz-selection, .cm-s-dracula .CodeMirror-line > span::-moz-selection, .cm-s-dracula .CodeMirror-line > span > span::-moz-selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-dracula span.cm-comment { color: #6272a4; }
.cm-s-dracula span.cm-string, .cm-s-dracula span.cm-string-2 { color: #f1fa8c; }
.cm-s-dracula span.cm-number { color: #bd93f9; }
.cm-s-dracula span.cm-variable { color: #50fa7b; }
.cm-s-dracula span.cm-variable-2 { color: white; }
.cm-s-dracula span.cm-def { color: #50fa7b; }
.cm-s-dracula span.cm-operator { color: #ff79c6; }
.cm-s-dracula span.cm-keyword { color: #ff79c6; }
.cm-s-dracula span.cm-atom { color: #bd93f9; }
.cm-s-dracula span.cm-meta { color: #f8f8f2; }
.cm-s-dracula span.cm-tag { color: #ff79c6; }
.cm-s-dracula span.cm-attribute { color: #50fa7b; }
.cm-s-dracula span.cm-qualifier { color: #50fa7b; }
.cm-s-dracula span.cm-property { color: #66d9ef; }
.cm-s-dracula span.cm-builtin { color: #50fa7b; }
.cm-s-dracula span.cm-variable-3, .cm-s-dracula span.cm-type { color: #ffb86c; }

.cm-s-dracula .CodeMirror-activeline-background { background: rgba(255,255,255,0.1); }
.cm-s-dracula .CodeMirror-matchingbracket { text-decoration: underline; color: white !important; }

/*

    Name:       Hopscotch
    Author:     Jan T. Sott

    CodeMirror template by Jan T. Sott (https://github.com/idleberg/base16-codemirror)
    Original Base16 color scheme by Chris Kempson (https://github.com/chriskempson/base16)

*/

.cm-s-hopscotch.CodeMirror {background: #322931; color: #d5d3d5;}
.cm-s-hopscotch div.CodeMirror-selected {background: #433b42 !important;}
.cm-s-hopscotch .CodeMirror-gutters {background: #322931; border-right: 0px;}
.cm-s-hopscotch .CodeMirror-linenumber {color: #797379;}
.cm-s-hopscotch .CodeMirror-cursor {border-left: 1px solid #989498 !important;}

.cm-s-hopscotch span.cm-comment {color: #b33508;}
.cm-s-hopscotch span.cm-atom {color: #c85e7c;}
.cm-s-hopscotch span.cm-number {color: #c85e7c;}

.cm-s-hopscotch span.cm-property, .cm-s-hopscotch span.cm-attribute {color: #8fc13e;}
.cm-s-hopscotch span.cm-keyword {color: #dd464c;}
.cm-s-hopscotch span.cm-string {color: #fdcc59;}

.cm-s-hopscotch span.cm-variable {color: #8fc13e;}
.cm-s-hopscotch span.cm-variable-2 {color: #1290bf;}
.cm-s-hopscotch span.cm-def {color: #fd8b19;}
.cm-s-hopscotch span.cm-error {background: #dd464c; color: #989498;}
.cm-s-hopscotch span.cm-bracket {color: #d5d3d5;}
.cm-s-hopscotch span.cm-tag {color: #dd464c;}
.cm-s-hopscotch span.cm-link {color: #c85e7c;}

.cm-s-hopscotch .CodeMirror-matchingbracket { text-decoration: underline; color: white !important;}
.cm-s-hopscotch .CodeMirror-activeline-background { background: #302020; }

/****************************************************************/
/*   Based on mbonaci's Brackets mbo theme                      */
/*   https://github.com/mbonaci/global/blob/master/Mbo.tmTheme  */
/*   Create your own: http://tmtheme-editor.herokuapp.com       */
/****************************************************************/

.cm-s-mbo.CodeMirror { background: #2c2c2c; color: #ffffec; }
.cm-s-mbo div.CodeMirror-selected { background: #716C62; }
.cm-s-mbo .CodeMirror-line::selection, .cm-s-mbo .CodeMirror-line > span::selection, .cm-s-mbo .CodeMirror-line > span > span::selection { background: rgba(113, 108, 98, .99); }
.cm-s-mbo .CodeMirror-line::-moz-selection, .cm-s-mbo .CodeMirror-line > span::-moz-selection, .cm-s-mbo .CodeMirror-line > span > span::-moz-selection { background: rgba(113, 108, 98, .99); }
.cm-s-mbo .CodeMirror-gutters { background: #4e4e4e; border-right: 0px; }
.cm-s-mbo .CodeMirror-guttermarker { color: white; }
.cm-s-mbo .CodeMirror-guttermarker-subtle { color: grey; }
.cm-s-mbo .CodeMirror-linenumber { color: #dadada; }
.cm-s-mbo .CodeMirror-cursor { border-left: 1px solid #ffffec; }

.cm-s-mbo span.cm-comment { color: #95958a; }
.cm-s-mbo span.cm-atom { color: #00a8c6; }
.cm-s-mbo span.cm-number { color: #00a8c6; }

.cm-s-mbo span.cm-property, .cm-s-mbo span.cm-attribute { color: #9ddfe9; }
.cm-s-mbo span.cm-keyword { color: #ffb928; }
.cm-s-mbo span.cm-string { color: #ffcf6c; }
.cm-s-mbo span.cm-string.cm-property { color: #ffffec; }

.cm-s-mbo span.cm-variable { color: #ffffec; }
.cm-s-mbo span.cm-variable-2 { color: #00a8c6; }
.cm-s-mbo span.cm-def { color: #ffffec; }
.cm-s-mbo span.cm-bracket { color: #fffffc; font-weight: bold; }
.cm-s-mbo span.cm-tag { color: #9ddfe9; }
.cm-s-mbo span.cm-link { color: #f54b07; }
.cm-s-mbo span.cm-error { border-bottom: #636363; color: #ffffec; }
.cm-s-mbo span.cm-qualifier { color: #ffffec; }

.cm-s-mbo .CodeMirror-activeline-background { background: #494b41; }
.cm-s-mbo .CodeMirror-matchingbracket { color: #ffb928 !important; }
.cm-s-mbo .CodeMirror-matchingtag { background: rgba(255, 255, 255, .37); }

/*
  MDN-LIKE Theme - Mozilla
  Ported to CodeMirror by Peter Kroon <plakroon@gmail.com>
  Report bugs/issues here: https://github.com/codemirror/CodeMirror/issues
  GitHub: @peterkroon

  The mdn-like theme is inspired on the displayed code examples at: https://developer.mozilla.org/en-US/docs/Web/CSS/animation

*/
.cm-s-mdn-like.CodeMirror { color: #999; background-color: #fff; }
.cm-s-mdn-like div.CodeMirror-selected { background: #cfc; }
.cm-s-mdn-like .CodeMirror-line::selection, .cm-s-mdn-like .CodeMirror-line > span::selection, .cm-s-mdn-like .CodeMirror-line > span > span::selection { background: #cfc; }
.cm-s-mdn-like .CodeMirror-line::-moz-selection, .cm-s-mdn-like .CodeMirror-line > span::-moz-selection, .cm-s-mdn-like .CodeMirror-line > span > span::-moz-selection { background: #cfc; }

.cm-s-mdn-like .CodeMirror-gutters { background: #f8f8f8; border-left: 6px solid rgba(0,83,159,0.65); color: #333; }
.cm-s-mdn-like .CodeMirror-linenumber { color: #aaa; padding-left: 8px; }
.cm-s-mdn-like .CodeMirror-cursor { border-left: 2px solid #222; }

.cm-s-mdn-like .cm-keyword { color: #6262FF; }
.cm-s-mdn-like .cm-atom { color: #F90; }
.cm-s-mdn-like .cm-number { color:  #ca7841; }
.cm-s-mdn-like .cm-def { color: #8DA6CE; }
.cm-s-mdn-like span.cm-variable-2, .cm-s-mdn-like span.cm-tag { color: #690; }
.cm-s-mdn-like span.cm-variable-3, .cm-s-mdn-like span.cm-def, .cm-s-mdn-like span.cm-type { color: #07a; }

.cm-s-mdn-like .cm-variable { color: #07a; }
.cm-s-mdn-like .cm-property { color: #905; }
.cm-s-mdn-like .cm-qualifier { color: #690; }

.cm-s-mdn-like .cm-operator { color: #cda869; }
.cm-s-mdn-like .cm-comment { color:#777; font-weight:normal; }
.cm-s-mdn-like .cm-string { color:#07a; font-style:italic; }
.cm-s-mdn-like .cm-string-2 { color:#bd6b18; } /*?*/
.cm-s-mdn-like .cm-meta { color: #000; } /*?*/
.cm-s-mdn-like .cm-builtin { color: #9B7536; } /*?*/
.cm-s-mdn-like .cm-tag { color: #997643; }
.cm-s-mdn-like .cm-attribute { color: #d6bb6d; } /*?*/
.cm-s-mdn-like .cm-header { color: #FF6400; }
.cm-s-mdn-like .cm-hr { color: #AEAEAE; }
.cm-s-mdn-like .cm-link { color:#ad9361; font-style:italic; text-decoration:none; }
.cm-s-mdn-like .cm-error { border-bottom: 1px solid red; }

div.cm-s-mdn-like .CodeMirror-activeline-background { background: #efefff; }
div.cm-s-mdn-like span.CodeMirror-matchingbracket { outline:1px solid grey; color: inherit; }

.cm-s-mdn-like.CodeMirror { background-image: url(data:image/png;base64,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); }

/*

    Name:       seti
    Author:     Michael Kaminsky (http://github.com/mkaminsky11)

    Original seti color scheme by Jesse Weed (https://github.com/jesseweed/seti-syntax)

*/


.cm-s-seti.CodeMirror {
  background-color: #151718 !important;
  color: #CFD2D1 !important;
  border: none;
}
.cm-s-seti .CodeMirror-gutters {
  color: #404b53;
  background-color: #0E1112;
  border: none;
}
.cm-s-seti .CodeMirror-cursor { border-left: solid thin #f8f8f0; }
.cm-s-seti .CodeMirror-linenumber { color: #6D8A88; }
.cm-s-seti.CodeMirror-focused div.CodeMirror-selected { background: rgba(255, 255, 255, 0.10); }
.cm-s-seti .CodeMirror-line::selection, .cm-s-seti .CodeMirror-line > span::selection, .cm-s-seti .CodeMirror-line > span > span::selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-seti .CodeMirror-line::-moz-selection, .cm-s-seti .CodeMirror-line > span::-moz-selection, .cm-s-seti .CodeMirror-line > span > span::-moz-selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-seti span.cm-comment { color: #41535b; }
.cm-s-seti span.cm-string, .cm-s-seti span.cm-string-2 { color: #55b5db; }
.cm-s-seti span.cm-number { color: #cd3f45; }
.cm-s-seti span.cm-variable { color: #55b5db; }
.cm-s-seti span.cm-variable-2 { color: #a074c4; }
.cm-s-seti span.cm-def { color: #55b5db; }
.cm-s-seti span.cm-keyword { color: #ff79c6; }
.cm-s-seti span.cm-operator { color: #9fca56; }
.cm-s-seti span.cm-keyword { color: #e6cd69; }
.cm-s-seti span.cm-atom { color: #cd3f45; }
.cm-s-seti span.cm-meta { color: #55b5db; }
.cm-s-seti span.cm-tag { color: #55b5db; }
.cm-s-seti span.cm-attribute { color: #9fca56; }
.cm-s-seti span.cm-qualifier { color: #9fca56; }
.cm-s-seti span.cm-property { color: #a074c4; }
.cm-s-seti span.cm-variable-3, .cm-s-seti span.cm-type { color: #9fca56; }
.cm-s-seti span.cm-builtin { color: #9fca56; }
.cm-s-seti .CodeMirror-activeline-background { background: #101213; }
.cm-s-seti .CodeMirror-matchingbracket { text-decoration: underline; color: white !important; }

/*
Solarized theme for code-mirror
http://ethanschoonover.com/solarized
*/

/*
Solarized color palette
http://ethanschoonover.com/solarized/img/solarized-palette.png
*/

.solarized.base03 { color: #002b36; }
.solarized.base02 { color: #073642; }
.solarized.base01 { color: #586e75; }
.solarized.base00 { color: #657b83; }
.solarized.base0 { color: #839496; }
.solarized.base1 { color: #93a1a1; }
.solarized.base2 { color: #eee8d5; }
.solarized.base3  { color: #fdf6e3; }
.solarized.solar-yellow  { color: #b58900; }
.solarized.solar-orange  { color: #cb4b16; }
.solarized.solar-red { color: #dc322f; }
.solarized.solar-magenta { color: #d33682; }
.solarized.solar-violet  { color: #6c71c4; }
.solarized.solar-blue { color: #268bd2; }
.solarized.solar-cyan { color: #2aa198; }
.solarized.solar-green { color: #859900; }

/* Color scheme for code-mirror */

.cm-s-solarized {
  line-height: 1.45em;
  color-profile: sRGB;
  rendering-intent: auto;
}
.cm-s-solarized.cm-s-dark {
  color: #839496;
  background-color: #002b36;
  text-shadow: #002b36 0 1px;
}
.cm-s-solarized.cm-s-light {
  background-color: #fdf6e3;
  color: #657b83;
  text-shadow: #eee8d5 0 1px;
}

.cm-s-solarized .CodeMirror-widget {
  text-shadow: none;
}

.cm-s-solarized .cm-header { color: #586e75; }
.cm-s-solarized .cm-quote { color: #93a1a1; }

.cm-s-solarized .cm-keyword { color: #cb4b16; }
.cm-s-solarized .cm-atom { color: #d33682; }
.cm-s-solarized .cm-number { color: #d33682; }
.cm-s-solarized .cm-def { color: #2aa198; }

.cm-s-solarized .cm-variable { color: #839496; }
.cm-s-solarized .cm-variable-2 { color: #b58900; }
.cm-s-solarized .cm-variable-3, .cm-s-solarized .cm-type { color: #6c71c4; }

.cm-s-solarized .cm-property { color: #2aa198; }
.cm-s-solarized .cm-operator { color: #6c71c4; }

.cm-s-solarized .cm-comment { color: #586e75; font-style:italic; }

.cm-s-solarized .cm-string { color: #859900; }
.cm-s-solarized .cm-string-2 { color: #b58900; }

.cm-s-solarized .cm-meta { color: #859900; }
.cm-s-solarized .cm-qualifier { color: #b58900; }
.cm-s-solarized .cm-builtin { color: #d33682; }
.cm-s-solarized .cm-bracket { color: #cb4b16; }
.cm-s-solarized .CodeMirror-matchingbracket { color: #859900; }
.cm-s-solarized .CodeMirror-nonmatchingbracket { color: #dc322f; }
.cm-s-solarized .cm-tag { color: #93a1a1; }
.cm-s-solarized .cm-attribute { color: #2aa198; }
.cm-s-solarized .cm-hr {
  color: transparent;
  border-top: 1px solid #586e75;
  display: block;
}
.cm-s-solarized .cm-link { color: #93a1a1; cursor: pointer; }
.cm-s-solarized .cm-special { color: #6c71c4; }
.cm-s-solarized .cm-em {
  color: #999;
  text-decoration: underline;
  text-decoration-style: dotted;
}
.cm-s-solarized .cm-error,
.cm-s-solarized .cm-invalidchar {
  color: #586e75;
  border-bottom: 1px dotted #dc322f;
}

.cm-s-solarized.cm-s-dark div.CodeMirror-selected { background: #073642; }
.cm-s-solarized.cm-s-dark.CodeMirror ::selection { background: rgba(7, 54, 66, 0.99); }
.cm-s-solarized.cm-s-dark .CodeMirror-line::-moz-selection, .cm-s-dark .CodeMirror-line > span::-moz-selection, .cm-s-dark .CodeMirror-line > span > span::-moz-selection { background: rgba(7, 54, 66, 0.99); }

.cm-s-solarized.cm-s-light div.CodeMirror-selected { background: #eee8d5; }
.cm-s-solarized.cm-s-light .CodeMirror-line::selection, .cm-s-light .CodeMirror-line > span::selection, .cm-s-light .CodeMirror-line > span > span::selection { background: #eee8d5; }
.cm-s-solarized.cm-s-light .CodeMirror-line::-moz-selection, .cm-s-ligh .CodeMirror-line > span::-moz-selection, .cm-s-ligh .CodeMirror-line > span > span::-moz-selection { background: #eee8d5; }

/* Editor styling */



/* Little shadow on the view-port of the buffer view */
.cm-s-solarized.CodeMirror {
  -moz-box-shadow: inset 7px 0 12px -6px #000;
  -webkit-box-shadow: inset 7px 0 12px -6px #000;
  box-shadow: inset 7px 0 12px -6px #000;
}

/* Remove gutter border */
.cm-s-solarized .CodeMirror-gutters {
  border-right: 0;
}

/* Gutter colors and line number styling based of color scheme (dark / light) */

/* Dark */
.cm-s-solarized.cm-s-dark .CodeMirror-gutters {
  background-color: #073642;
}

.cm-s-solarized.cm-s-dark .CodeMirror-linenumber {
  color: #586e75;
  text-shadow: #021014 0 -1px;
}

/* Light */
.cm-s-solarized.cm-s-light .CodeMirror-gutters {
  background-color: #eee8d5;
}

.cm-s-solarized.cm-s-light .CodeMirror-linenumber {
  color: #839496;
}

/* Common */
.cm-s-solarized .CodeMirror-linenumber {
  padding: 0 5px;
}
.cm-s-solarized .CodeMirror-guttermarker-subtle { color: #586e75; }
.cm-s-solarized.cm-s-dark .CodeMirror-guttermarker { color: #ddd; }
.cm-s-solarized.cm-s-light .CodeMirror-guttermarker { color: #cb4b16; }

.cm-s-solarized .CodeMirror-gutter .CodeMirror-gutter-text {
  color: #586e75;
}

/* Cursor */
.cm-s-solarized .CodeMirror-cursor { border-left: 1px solid #819090; }

/* Fat cursor */
.cm-s-solarized.cm-s-light.cm-fat-cursor .CodeMirror-cursor { background: #77ee77; }
.cm-s-solarized.cm-s-light .cm-animate-fat-cursor { background-color: #77ee77; }
.cm-s-solarized.cm-s-dark.cm-fat-cursor .CodeMirror-cursor { background: #586e75; }
.cm-s-solarized.cm-s-dark .cm-animate-fat-cursor { background-color: #586e75; }

/* Active line */
.cm-s-solarized.cm-s-dark .CodeMirror-activeline-background {
  background: rgba(255, 255, 255, 0.06);
}
.cm-s-solarized.cm-s-light .CodeMirror-activeline-background {
  background: rgba(0, 0, 0, 0.06);
}

.cm-s-the-matrix.CodeMirror { background: #000000; color: #00FF00; }
.cm-s-the-matrix div.CodeMirror-selected { background: #2D2D2D; }
.cm-s-the-matrix .CodeMirror-line::selection, .cm-s-the-matrix .CodeMirror-line > span::selection, .cm-s-the-matrix .CodeMirror-line > span > span::selection { background: rgba(45, 45, 45, 0.99); }
.cm-s-the-matrix .CodeMirror-line::-moz-selection, .cm-s-the-matrix .CodeMirror-line > span::-moz-selection, .cm-s-the-matrix .CodeMirror-line > span > span::-moz-selection { background: rgba(45, 45, 45, 0.99); }
.cm-s-the-matrix .CodeMirror-gutters { background: #060; border-right: 2px solid #00FF00; }
.cm-s-the-matrix .CodeMirror-guttermarker { color: #0f0; }
.cm-s-the-matrix .CodeMirror-guttermarker-subtle { color: white; }
.cm-s-the-matrix .CodeMirror-linenumber { color: #FFFFFF; }
.cm-s-the-matrix .CodeMirror-cursor { border-left: 1px solid #00FF00; }

.cm-s-the-matrix span.cm-keyword { color: #008803; font-weight: bold; }
.cm-s-the-matrix span.cm-atom { color: #3FF; }
.cm-s-the-matrix span.cm-number { color: #FFB94F; }
.cm-s-the-matrix span.cm-def { color: #99C; }
.cm-s-the-matrix span.cm-variable { color: #F6C; }
.cm-s-the-matrix span.cm-variable-2 { color: #C6F; }
.cm-s-the-matrix span.cm-variable-3, .cm-s-the-matrix span.cm-type { color: #96F; }
.cm-s-the-matrix span.cm-property { color: #62FFA0; }
.cm-s-the-matrix span.cm-operator { color: #999; }
.cm-s-the-matrix span.cm-comment { color: #CCCCCC; }
.cm-s-the-matrix span.cm-string { color: #39C; }
.cm-s-the-matrix span.cm-meta { color: #C9F; }
.cm-s-the-matrix span.cm-qualifier { color: #FFF700; }
.cm-s-the-matrix span.cm-builtin { color: #30a; }
.cm-s-the-matrix span.cm-bracket { color: #cc7; }
.cm-s-the-matrix span.cm-tag { color: #FFBD40; }
.cm-s-the-matrix span.cm-attribute { color: #FFF700; }
.cm-s-the-matrix span.cm-error { color: #FF0000; }

.cm-s-the-matrix .CodeMirror-activeline-background { background: #040; }

/*
Copyright (C) 2011 by MarkLogic Corporation
Author: Mike Brevoort <mike@brevoort.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
*/
.cm-s-xq-light span.cm-keyword { line-height: 1em; font-weight: bold; color: #5A5CAD; }
.cm-s-xq-light span.cm-atom { color: #6C8CD5; }
.cm-s-xq-light span.cm-number { color: #164; }
.cm-s-xq-light span.cm-def { text-decoration:underline; }
.cm-s-xq-light span.cm-variable { color: black; }
.cm-s-xq-light span.cm-variable-2 { color:black; }
.cm-s-xq-light span.cm-variable-3, .cm-s-xq-light span.cm-type { color: black; }
.cm-s-xq-light span.cm-property {}
.cm-s-xq-light span.cm-operator {}
.cm-s-xq-light span.cm-comment { color: #0080FF; font-style: italic; }
.cm-s-xq-light span.cm-string { color: red; }
.cm-s-xq-light span.cm-meta { color: yellow; }
.cm-s-xq-light span.cm-qualifier { color: grey; }
.cm-s-xq-light span.cm-builtin { color: #7EA656; }
.cm-s-xq-light span.cm-bracket { color: #cc7; }
.cm-s-xq-light span.cm-tag { color: #3F7F7F; }
.cm-s-xq-light span.cm-attribute { color: #7F007F; }
.cm-s-xq-light span.cm-error { color: #f00; }

.cm-s-xq-light .CodeMirror-activeline-background { background: #e8f2ff; }
.cm-s-xq-light .CodeMirror-matchingbracket { outline:1px solid grey;color:black !important;background:yellow; }

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.CodeMirror {
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  border: 0;
  border-radius: 0;
  height: auto;
  /* Changed to auto to autogrow */
}

.CodeMirror pre {
  padding: 0 var(--jp-code-padding);
}

.jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-dialog {
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
}

/* This causes https://github.com/jupyter/jupyterlab/issues/522 */
/* May not cause it not because we changed it! */
.CodeMirror-lines {
  padding: var(--jp-code-padding) 0;
}

.CodeMirror-linenumber {
  padding: 0 8px;
}

.jp-CodeMirrorEditor-static {
  margin: var(--jp-code-padding);
}

.jp-CodeMirrorEditor,
.jp-CodeMirrorEditor-static {
  cursor: text;
}

.jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
  border-left: var(--jp-code-cursor-width0) solid var(--jp-editor-cursor-color);
}

/* When zoomed out 67% and 33% on a screen of 1440 width x 900 height */
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
    border-left: var(--jp-code-cursor-width1) solid
      var(--jp-editor-cursor-color);
  }
}

/* When zoomed out less than 33% */
@media screen and (min-width: 4320px) {
  .jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
    border-left: var(--jp-code-cursor-width2) solid
      var(--jp-editor-cursor-color);
  }
}

.CodeMirror.jp-mod-readOnly .CodeMirror-cursor {
  display: none;
}

.CodeMirror-gutters {
  border-right: 1px solid var(--jp-border-color2);
  background-color: var(--jp-layout-color0);
}

.jp-CollaboratorCursor {
  border-left: 5px solid transparent;
  border-right: 5px solid transparent;
  border-top: none;
  border-bottom: 3px solid;
  background-clip: content-box;
  margin-left: -5px;
  margin-right: -5px;
}

.CodeMirror-selectedtext.cm-searching {
  background-color: var(--jp-search-selected-match-background-color) !important;
  color: var(--jp-search-selected-match-color) !important;
}

.cm-searching {
  background-color: var(
    --jp-search-unselected-match-background-color
  ) !important;
  color: var(--jp-search-unselected-match-color) !important;
}

.CodeMirror-focused .CodeMirror-selected {
  background-color: var(--jp-editor-selected-focused-background);
}

.CodeMirror-selected {
  background-color: var(--jp-editor-selected-background);
}

.jp-CollaboratorCursor-hover {
  position: absolute;
  z-index: 1;
  transform: translateX(-50%);
  color: white;
  border-radius: 3px;
  padding-left: 4px;
  padding-right: 4px;
  padding-top: 1px;
  padding-bottom: 1px;
  text-align: center;
  font-size: var(--jp-ui-font-size1);
  white-space: nowrap;
}

.jp-CodeMirror-ruler {
  border-left: 1px dashed var(--jp-border-color2);
}

/**
 * Here is our jupyter theme for CodeMirror syntax highlighting
 * This is used in our marked.js syntax highlighting and CodeMirror itself
 * The string "jupyter" is set in ../codemirror/widget.DEFAULT_CODEMIRROR_THEME
 * This came from the classic notebook, which came form highlight.js/GitHub
 */

/**
 * CodeMirror themes are handling the background/color in this way. This works
 * fine for CodeMirror editors outside the notebook, but the notebook styles
 * these things differently.
 */
.CodeMirror.cm-s-jupyter {
  background: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
}

/* In the notebook, we want this styling to be handled by its container */
.jp-CodeConsole .CodeMirror.cm-s-jupyter,
.jp-Notebook .CodeMirror.cm-s-jupyter {
  background: transparent;
}

.cm-s-jupyter .CodeMirror-cursor {
  border-left: var(--jp-code-cursor-width0) solid var(--jp-editor-cursor-color);
}
.cm-s-jupyter span.cm-keyword {
  color: var(--jp-mirror-editor-keyword-color);
  font-weight: bold;
}
.cm-s-jupyter span.cm-atom {
  color: var(--jp-mirror-editor-atom-color);
}
.cm-s-jupyter span.cm-number {
  color: var(--jp-mirror-editor-number-color);
}
.cm-s-jupyter span.cm-def {
  color: var(--jp-mirror-editor-def-color);
}
.cm-s-jupyter span.cm-variable {
  color: var(--jp-mirror-editor-variable-color);
}
.cm-s-jupyter span.cm-variable-2 {
  color: var(--jp-mirror-editor-variable-2-color);
}
.cm-s-jupyter span.cm-variable-3 {
  color: var(--jp-mirror-editor-variable-3-color);
}
.cm-s-jupyter span.cm-punctuation {
  color: var(--jp-mirror-editor-punctuation-color);
}
.cm-s-jupyter span.cm-property {
  color: var(--jp-mirror-editor-property-color);
}
.cm-s-jupyter span.cm-operator {
  color: var(--jp-mirror-editor-operator-color);
  font-weight: bold;
}
.cm-s-jupyter span.cm-comment {
  color: var(--jp-mirror-editor-comment-color);
  font-style: italic;
}
.cm-s-jupyter span.cm-string {
  color: var(--jp-mirror-editor-string-color);
}
.cm-s-jupyter span.cm-string-2 {
  color: var(--jp-mirror-editor-string-2-color);
}
.cm-s-jupyter span.cm-meta {
  color: var(--jp-mirror-editor-meta-color);
}
.cm-s-jupyter span.cm-qualifier {
  color: var(--jp-mirror-editor-qualifier-color);
}
.cm-s-jupyter span.cm-builtin {
  color: var(--jp-mirror-editor-builtin-color);
}
.cm-s-jupyter span.cm-bracket {
  color: var(--jp-mirror-editor-bracket-color);
}
.cm-s-jupyter span.cm-tag {
  color: var(--jp-mirror-editor-tag-color);
}
.cm-s-jupyter span.cm-attribute {
  color: var(--jp-mirror-editor-attribute-color);
}
.cm-s-jupyter span.cm-header {
  color: var(--jp-mirror-editor-header-color);
}
.cm-s-jupyter span.cm-quote {
  color: var(--jp-mirror-editor-quote-color);
}
.cm-s-jupyter span.cm-link {
  color: var(--jp-mirror-editor-link-color);
}
.cm-s-jupyter span.cm-error {
  color: var(--jp-mirror-editor-error-color);
}
.cm-s-jupyter span.cm-hr {
  color: #999;
}

.cm-s-jupyter span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}

.cm-s-jupyter .CodeMirror-activeline-background,
.cm-s-jupyter .CodeMirror-gutter {
  background-color: var(--jp-layout-color2);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| RenderedText
|----------------------------------------------------------------------------*/

.jp-RenderedText {
  text-align: left;
  padding-left: var(--jp-code-padding);
  line-height: var(--jp-code-line-height);
  font-family: var(--jp-code-font-family);
}

.jp-RenderedText pre,
.jp-RenderedJavaScript pre,
.jp-RenderedHTMLCommon pre {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-code-font-size);
  border: none;
  margin: 0px;
  padding: 0px;
  line-height: normal;
}

.jp-RenderedText pre a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}
.jp-RenderedText pre a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}
.jp-RenderedText pre a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* console foregrounds and backgrounds */
.jp-RenderedText pre .ansi-black-fg {
  color: #3e424d;
}
.jp-RenderedText pre .ansi-red-fg {
  color: #e75c58;
}
.jp-RenderedText pre .ansi-green-fg {
  color: #00a250;
}
.jp-RenderedText pre .ansi-yellow-fg {
  color: #ddb62b;
}
.jp-RenderedText pre .ansi-blue-fg {
  color: #208ffb;
}
.jp-RenderedText pre .ansi-magenta-fg {
  color: #d160c4;
}
.jp-RenderedText pre .ansi-cyan-fg {
  color: #60c6c8;
}
.jp-RenderedText pre .ansi-white-fg {
  color: #c5c1b4;
}

.jp-RenderedText pre .ansi-black-bg {
  background-color: #3e424d;
}
.jp-RenderedText pre .ansi-red-bg {
  background-color: #e75c58;
}
.jp-RenderedText pre .ansi-green-bg {
  background-color: #00a250;
}
.jp-RenderedText pre .ansi-yellow-bg {
  background-color: #ddb62b;
}
.jp-RenderedText pre .ansi-blue-bg {
  background-color: #208ffb;
}
.jp-RenderedText pre .ansi-magenta-bg {
  background-color: #d160c4;
}
.jp-RenderedText pre .ansi-cyan-bg {
  background-color: #60c6c8;
}
.jp-RenderedText pre .ansi-white-bg {
  background-color: #c5c1b4;
}

.jp-RenderedText pre .ansi-black-intense-fg {
  color: #282c36;
}
.jp-RenderedText pre .ansi-red-intense-fg {
  color: #b22b31;
}
.jp-RenderedText pre .ansi-green-intense-fg {
  color: #007427;
}
.jp-RenderedText pre .ansi-yellow-intense-fg {
  color: #b27d12;
}
.jp-RenderedText pre .ansi-blue-intense-fg {
  color: #0065ca;
}
.jp-RenderedText pre .ansi-magenta-intense-fg {
  color: #a03196;
}
.jp-RenderedText pre .ansi-cyan-intense-fg {
  color: #258f8f;
}
.jp-RenderedText pre .ansi-white-intense-fg {
  color: #a1a6b2;
}

.jp-RenderedText pre .ansi-black-intense-bg {
  background-color: #282c36;
}
.jp-RenderedText pre .ansi-red-intense-bg {
  background-color: #b22b31;
}
.jp-RenderedText pre .ansi-green-intense-bg {
  background-color: #007427;
}
.jp-RenderedText pre .ansi-yellow-intense-bg {
  background-color: #b27d12;
}
.jp-RenderedText pre .ansi-blue-intense-bg {
  background-color: #0065ca;
}
.jp-RenderedText pre .ansi-magenta-intense-bg {
  background-color: #a03196;
}
.jp-RenderedText pre .ansi-cyan-intense-bg {
  background-color: #258f8f;
}
.jp-RenderedText pre .ansi-white-intense-bg {
  background-color: #a1a6b2;
}

.jp-RenderedText pre .ansi-default-inverse-fg {
  color: var(--jp-ui-inverse-font-color0);
}
.jp-RenderedText pre .ansi-default-inverse-bg {
  background-color: var(--jp-inverse-layout-color0);
}

.jp-RenderedText pre .ansi-bold {
  font-weight: bold;
}
.jp-RenderedText pre .ansi-underline {
  text-decoration: underline;
}

.jp-RenderedText[data-mime-type='application/vnd.jupyter.stderr'] {
  background: var(--jp-rendermime-error-background);
  padding-top: var(--jp-code-padding);
}

/*-----------------------------------------------------------------------------
| RenderedLatex
|----------------------------------------------------------------------------*/

.jp-RenderedLatex {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);
}

/* Left-justify outputs.*/
.jp-OutputArea-output.jp-RenderedLatex {
  padding: var(--jp-code-padding);
  text-align: left;
}

/*-----------------------------------------------------------------------------
| RenderedHTML
|----------------------------------------------------------------------------*/

.jp-RenderedHTMLCommon {
  color: var(--jp-content-font-color1);
  font-family: var(--jp-content-font-family);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);
  /* Give a bit more R padding on Markdown text to keep line lengths reasonable */
  padding-right: 20px;
}

.jp-RenderedHTMLCommon em {
  font-style: italic;
}

.jp-RenderedHTMLCommon strong {
  font-weight: bold;
}

.jp-RenderedHTMLCommon u {
  text-decoration: underline;
}

.jp-RenderedHTMLCommon a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* Headings */

.jp-RenderedHTMLCommon h1,
.jp-RenderedHTMLCommon h2,
.jp-RenderedHTMLCommon h3,
.jp-RenderedHTMLCommon h4,
.jp-RenderedHTMLCommon h5,
.jp-RenderedHTMLCommon h6 {
  line-height: var(--jp-content-heading-line-height);
  font-weight: var(--jp-content-heading-font-weight);
  font-style: normal;
  margin: var(--jp-content-heading-margin-top) 0
    var(--jp-content-heading-margin-bottom) 0;
}

.jp-RenderedHTMLCommon h1:first-child,
.jp-RenderedHTMLCommon h2:first-child,
.jp-RenderedHTMLCommon h3:first-child,
.jp-RenderedHTMLCommon h4:first-child,
.jp-RenderedHTMLCommon h5:first-child,
.jp-RenderedHTMLCommon h6:first-child {
  margin-top: calc(0.5 * var(--jp-content-heading-margin-top));
}

.jp-RenderedHTMLCommon h1:last-child,
.jp-RenderedHTMLCommon h2:last-child,
.jp-RenderedHTMLCommon h3:last-child,
.jp-RenderedHTMLCommon h4:last-child,
.jp-RenderedHTMLCommon h5:last-child,
.jp-RenderedHTMLCommon h6:last-child {
  margin-bottom: calc(0.5 * var(--jp-content-heading-margin-bottom));
}

.jp-RenderedHTMLCommon h1 {
  font-size: var(--jp-content-font-size5);
}

.jp-RenderedHTMLCommon h2 {
  font-size: var(--jp-content-font-size4);
}

.jp-RenderedHTMLCommon h3 {
  font-size: var(--jp-content-font-size3);
}

.jp-RenderedHTMLCommon h4 {
  font-size: var(--jp-content-font-size2);
}

.jp-RenderedHTMLCommon h5 {
  font-size: var(--jp-content-font-size1);
}

.jp-RenderedHTMLCommon h6 {
  font-size: var(--jp-content-font-size0);
}

/* Lists */

.jp-RenderedHTMLCommon ul:not(.list-inline),
.jp-RenderedHTMLCommon ol:not(.list-inline) {
  padding-left: 2em;
}

.jp-RenderedHTMLCommon ul {
  list-style: disc;
}

.jp-RenderedHTMLCommon ul ul {
  list-style: square;
}

.jp-RenderedHTMLCommon ul ul ul {
  list-style: circle;
}

.jp-RenderedHTMLCommon ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol ol {
  list-style: upper-alpha;
}

.jp-RenderedHTMLCommon ol ol ol {
  list-style: lower-alpha;
}

.jp-RenderedHTMLCommon ol ol ol ol {
  list-style: lower-roman;
}

.jp-RenderedHTMLCommon ol ol ol ol ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol,
.jp-RenderedHTMLCommon ul {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon ul ul,
.jp-RenderedHTMLCommon ul ol,
.jp-RenderedHTMLCommon ol ul,
.jp-RenderedHTMLCommon ol ol {
  margin-bottom: 0em;
}

.jp-RenderedHTMLCommon hr {
  color: var(--jp-border-color2);
  background-color: var(--jp-border-color1);
  margin-top: 1em;
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon > pre {
  margin: 1.5em 2em;
}

.jp-RenderedHTMLCommon pre,
.jp-RenderedHTMLCommon code {
  border: 0;
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  line-height: var(--jp-code-line-height);
  padding: 0;
  white-space: pre-wrap;
}

.jp-RenderedHTMLCommon :not(pre) > code {
  background-color: var(--jp-layout-color2);
  padding: 1px 5px;
}

/* Tables */

.jp-RenderedHTMLCommon table {
  border-collapse: collapse;
  border-spacing: 0;
  border: none;
  color: var(--jp-ui-font-color1);
  font-size: 12px;
  table-layout: fixed;
  margin-left: auto;
  margin-right: auto;
}

.jp-RenderedHTMLCommon thead {
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  vertical-align: bottom;
}

.jp-RenderedHTMLCommon td,
.jp-RenderedHTMLCommon th,
.jp-RenderedHTMLCommon tr {
  vertical-align: middle;
  padding: 0.5em 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}

.jp-RenderedMarkdown.jp-RenderedHTMLCommon td,
.jp-RenderedMarkdown.jp-RenderedHTMLCommon th {
  max-width: none;
}

:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon td,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon th,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon tr {
  text-align: right;
}

.jp-RenderedHTMLCommon th {
  font-weight: bold;
}

.jp-RenderedHTMLCommon tbody tr:nth-child(odd) {
  background: var(--jp-layout-color0);
}

.jp-RenderedHTMLCommon tbody tr:nth-child(even) {
  background: var(--jp-rendermime-table-row-background);
}

.jp-RenderedHTMLCommon tbody tr:hover {
  background: var(--jp-rendermime-table-row-hover-background);
}

.jp-RenderedHTMLCommon table {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon p {
  text-align: left;
  margin: 0px;
}

.jp-RenderedHTMLCommon p {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon img {
  -moz-force-broken-image-icon: 1;
}

/* Restrict to direct children as other images could be nested in other content. */
.jp-RenderedHTMLCommon > img {
  display: block;
  margin-left: 0;
  margin-right: 0;
  margin-bottom: 1em;
}

/* Change color behind transparent images if they need it... */
[data-jp-theme-light='false'] .jp-RenderedImage img.jp-needs-light-background {
  background-color: var(--jp-inverse-layout-color1);
}
[data-jp-theme-light='true'] .jp-RenderedImage img.jp-needs-dark-background {
  background-color: var(--jp-inverse-layout-color1);
}
/* ...or leave it untouched if they don't */
[data-jp-theme-light='false'] .jp-RenderedImage img.jp-needs-dark-background {
}
[data-jp-theme-light='true'] .jp-RenderedImage img.jp-needs-light-background {
}

.jp-RenderedHTMLCommon img,
.jp-RenderedImage img,
.jp-RenderedHTMLCommon svg,
.jp-RenderedSVG svg {
  max-width: 100%;
  height: auto;
}

.jp-RenderedHTMLCommon img.jp-mod-unconfined,
.jp-RenderedImage img.jp-mod-unconfined,
.jp-RenderedHTMLCommon svg.jp-mod-unconfined,
.jp-RenderedSVG svg.jp-mod-unconfined {
  max-width: none;
}

.jp-RenderedHTMLCommon .alert {
  padding: var(--jp-notebook-padding);
  border: var(--jp-border-width) solid transparent;
  border-radius: var(--jp-border-radius);
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon .alert-info {
  color: var(--jp-info-color0);
  background-color: var(--jp-info-color3);
  border-color: var(--jp-info-color2);
}
.jp-RenderedHTMLCommon .alert-info hr {
  border-color: var(--jp-info-color3);
}
.jp-RenderedHTMLCommon .alert-info > p:last-child,
.jp-RenderedHTMLCommon .alert-info > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-warning {
  color: var(--jp-warn-color0);
  background-color: var(--jp-warn-color3);
  border-color: var(--jp-warn-color2);
}
.jp-RenderedHTMLCommon .alert-warning hr {
  border-color: var(--jp-warn-color3);
}
.jp-RenderedHTMLCommon .alert-warning > p:last-child,
.jp-RenderedHTMLCommon .alert-warning > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-success {
  color: var(--jp-success-color0);
  background-color: var(--jp-success-color3);
  border-color: var(--jp-success-color2);
}
.jp-RenderedHTMLCommon .alert-success hr {
  border-color: var(--jp-success-color3);
}
.jp-RenderedHTMLCommon .alert-success > p:last-child,
.jp-RenderedHTMLCommon .alert-success > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-danger {
  color: var(--jp-error-color0);
  background-color: var(--jp-error-color3);
  border-color: var(--jp-error-color2);
}
.jp-RenderedHTMLCommon .alert-danger hr {
  border-color: var(--jp-error-color3);
}
.jp-RenderedHTMLCommon .alert-danger > p:last-child,
.jp-RenderedHTMLCommon .alert-danger > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon blockquote {
  margin: 1em 2em;
  padding: 0 1em;
  border-left: 5px solid var(--jp-border-color2);
}

a.jp-InternalAnchorLink {
  visibility: hidden;
  margin-left: 8px;
  color: var(--md-blue-800);
}

h1:hover .jp-InternalAnchorLink,
h2:hover .jp-InternalAnchorLink,
h3:hover .jp-InternalAnchorLink,
h4:hover .jp-InternalAnchorLink,
h5:hover .jp-InternalAnchorLink,
h6:hover .jp-InternalAnchorLink {
  visibility: visible;
}

.jp-RenderedHTMLCommon kbd {
  background-color: var(--jp-rendermime-table-row-background);
  border: 1px solid var(--jp-border-color0);
  border-bottom-color: var(--jp-border-color2);
  border-radius: 3px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
  display: inline-block;
  font-size: 0.8em;
  line-height: 1em;
  padding: 0.2em 0.5em;
}

/* Most direct children of .jp-RenderedHTMLCommon have a margin-bottom of 1.0.
 * At the bottom of cells this is a bit too much as there is also spacing
 * between cells. Going all the way to 0 gets too tight between markdown and
 * code cells.
 */
.jp-RenderedHTMLCommon > *:last-child {
  margin-bottom: 0.5em;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MimeDocument {
  outline: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-filebrowser-button-height: 28px;
  --jp-private-filebrowser-button-width: 48px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-FileBrowser {
  display: flex;
  flex-direction: column;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
}

.jp-FileBrowser-toolbar.jp-Toolbar {
  border-bottom: none;
  height: auto;
  margin: var(--jp-toolbar-header-margin);
  box-shadow: none;
}

.jp-BreadCrumbs {
  flex: 0 0 auto;
  margin: 4px 12px;
}

.jp-BreadCrumbs-item {
  margin: 0px 2px;
  padding: 0px 2px;
  border-radius: var(--jp-border-radius);
  cursor: pointer;
}

.jp-BreadCrumbs-item:hover {
  background-color: var(--jp-layout-color2);
}

.jp-BreadCrumbs-item:first-child {
  margin-left: 0px;
}

.jp-BreadCrumbs-item.jp-mod-dropTarget {
  background-color: var(--jp-brand-color2);
  opacity: 0.7;
}

/*-----------------------------------------------------------------------------
| Buttons
|----------------------------------------------------------------------------*/

.jp-FileBrowser-toolbar.jp-Toolbar {
  padding: 0px;
}

.jp-FileBrowser-toolbar.jp-Toolbar {
  justify-content: space-evenly;
}

.jp-FileBrowser-toolbar.jp-Toolbar .jp-Toolbar-item {
  flex: 1;
}

.jp-FileBrowser-toolbar.jp-Toolbar .jp-ToolbarButtonComponent {
  width: 100%;
}

/*-----------------------------------------------------------------------------
| DirListing
|----------------------------------------------------------------------------*/

.jp-DirListing {
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
  outline: 0;
}

.jp-DirListing-header {
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  overflow: hidden;
  border-top: var(--jp-border-width) solid var(--jp-border-color2);
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  box-shadow: var(--jp-toolbar-box-shadow);
  z-index: 2;
}

.jp-DirListing-headerItem {
  padding: 4px 12px 2px 12px;
  font-weight: 500;
}

.jp-DirListing-headerItem:hover {
  background: var(--jp-layout-color2);
}

.jp-DirListing-headerItem.jp-id-name {
  flex: 1 0 84px;
}

.jp-DirListing-headerItem.jp-id-modified {
  flex: 0 0 112px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
}

.jp-DirListing-narrow .jp-id-modified,
.jp-DirListing-narrow .jp-DirListing-itemModified {
  display: none;
}

.jp-DirListing-headerItem.jp-mod-selected {
  font-weight: 600;
}

/* increase specificity to override bundled default */
.jp-DirListing-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  list-style-type: none;
  overflow: auto;
  background-color: var(--jp-layout-color1);
}

/* Style the directory listing content when a user drops a file to upload */
.jp-DirListing.jp-mod-native-drop .jp-DirListing-content {
  outline: 5px dashed rgba(128, 128, 128, 0.5);
  outline-offset: -10px;
  cursor: copy;
}

.jp-DirListing-item {
  display: flex;
  flex-direction: row;
  padding: 4px 12px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-DirListing-item.jp-mod-selected {
  color: white;
  background: var(--jp-brand-color1);
}

.jp-DirListing-item.jp-mod-dropTarget {
  background: var(--jp-brand-color3);
}

.jp-DirListing-item:hover:not(.jp-mod-selected) {
  background: var(--jp-layout-color2);
}

.jp-DirListing-itemIcon {
  flex: 0 0 20px;
  margin-right: 4px;
}

.jp-DirListing-itemText {
  flex: 1 0 64px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  user-select: none;
}

.jp-DirListing-itemModified {
  flex: 0 0 125px;
  text-align: right;
}

.jp-DirListing-editor {
  flex: 1 0 64px;
  outline: none;
  border: none;
}

.jp-DirListing-item.jp-mod-running .jp-DirListing-itemIcon:before {
  color: limegreen;
  content: '\25CF';
  font-size: 8px;
  position: absolute;
  left: -8px;
}

.jp-DirListing-item.lm-mod-drag-image,
.jp-DirListing-item.jp-mod-selected.lm-mod-drag-image {
  font-size: var(--jp-ui-font-size1);
  padding-left: 4px;
  margin-left: 4px;
  width: 160px;
  background-color: var(--jp-ui-inverse-font-color2);
  box-shadow: var(--jp-elevation-z2);
  border-radius: 0px;
  color: var(--jp-ui-font-color1);
  transform: translateX(-40%) translateY(-58%);
}

.jp-DirListing-deadSpace {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  list-style-type: none;
  overflow: auto;
  background-color: var(--jp-layout-color1);
}

.jp-Document {
  min-width: 120px;
  min-height: 120px;
  outline: none;
}

.jp-FileDialog.jp-mod-conflict input {
  color: red;
}

.jp-FileDialog .jp-new-name-title {
  margin-top: 12px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
}

/*-----------------------------------------------------------------------------
| Main OutputArea
| OutputArea has a list of Outputs
|----------------------------------------------------------------------------*/

.jp-OutputArea {
  overflow-y: auto;
}

.jp-OutputArea-child {
  display: flex;
  flex-direction: row;
}

.jp-OutputPrompt {
  flex: 0 0 var(--jp-cell-prompt-width);
  color: var(--jp-cell-outprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
  opacity: var(--jp-cell-prompt-opacity);
  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-OutputArea-output {
  height: auto;
  overflow: auto;
  user-select: text;
  -moz-user-select: text;
  -webkit-user-select: text;
  -ms-user-select: text;
}

.jp-OutputArea-child .jp-OutputArea-output {
  flex-grow: 1;
  flex-shrink: 1;
}

/**
 * Isolated output.
 */
.jp-OutputArea-output.jp-mod-isolated {
  width: 100%;
  display: block;
}

/*
When drag events occur, `p-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated {
  position: relative;
}

body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

/* pre */

.jp-OutputArea-output pre {
  border: none;
  margin: 0px;
  padding: 0px;
  overflow-x: auto;
  overflow-y: auto;
  word-break: break-all;
  word-wrap: break-word;
  white-space: pre-wrap;
}

/* tables */

.jp-OutputArea-output.jp-RenderedHTMLCommon table {
  margin-left: 0;
  margin-right: 0;
}

/* description lists */

.jp-OutputArea-output dl,
.jp-OutputArea-output dt,
.jp-OutputArea-output dd {
  display: block;
}

.jp-OutputArea-output dl {
  width: 100%;
  overflow: hidden;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dt {
  font-weight: bold;
  float: left;
  width: 20%;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dd {
  float: left;
  width: 80%;
  padding: 0;
  margin: 0;
}

/* Hide the gutter in case of
 *  - nested output areas (e.g. in the case of output widgets)
 *  - mirrored output areas
 */
.jp-OutputArea .jp-OutputArea .jp-OutputArea-prompt {
  display: none;
}

/*-----------------------------------------------------------------------------
| executeResult is added to any Output-result for the display of the object
| returned by a cell
|----------------------------------------------------------------------------*/

.jp-OutputArea-output.jp-OutputArea-executeResult {
  margin-left: 0px;
  flex: 1 1 auto;
}

.jp-OutputArea-executeResult.jp-RenderedText {
  padding-top: var(--jp-code-padding);
}

/*-----------------------------------------------------------------------------
| The Stdin output
|----------------------------------------------------------------------------*/

.jp-OutputArea-stdin {
  line-height: var(--jp-code-line-height);
  padding-top: var(--jp-code-padding);
  display: flex;
}

.jp-Stdin-prompt {
  color: var(--jp-content-font-color0);
  padding-right: var(--jp-code-padding);
  vertical-align: baseline;
  flex: 0 0 auto;
}

.jp-Stdin-input {
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  color: inherit;
  background-color: inherit;
  width: 42%;
  min-width: 200px;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
  flex: 0 0 70%;
}

.jp-Stdin-input:focus {
  box-shadow: none;
}

/*-----------------------------------------------------------------------------
| Output Area View
|----------------------------------------------------------------------------*/

.jp-LinkedOutputView .jp-OutputArea {
  height: 100%;
  display: block;
}

.jp-LinkedOutputView .jp-OutputArea-output:only-child {
  height: 100%;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapser {
  flex: 0 0 var(--jp-cell-collapser-width);
  padding: 0px;
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
  border-radius: var(--jp-border-radius);
  opacity: 1;
}

.jp-Collapser-child {
  display: block;
  width: 100%;
  box-sizing: border-box;
  /* height: 100% doesn't work because the height of its parent is computed from content */
  position: absolute;
  top: 0px;
  bottom: 0px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Header/Footer
|----------------------------------------------------------------------------*/

/* Hidden by zero height by default */
.jp-CellHeader,
.jp-CellFooter {
  height: 0px;
  width: 100%;
  padding: 0px;
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Input
|----------------------------------------------------------------------------*/

/* All input areas */
.jp-InputArea {
  display: flex;
  flex-direction: row;
}

.jp-InputArea-editor {
  flex: 1 1 auto;
}

.jp-InputArea-editor {
  /* This is the non-active, default styling */
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  border-radius: 0px;
  background: var(--jp-cell-editor-background);
}

.jp-InputPrompt {
  flex: 0 0 var(--jp-cell-prompt-width);
  color: var(--jp-cell-inprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  opacity: var(--jp-cell-prompt-opacity);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
  opacity: var(--jp-cell-prompt-opacity);
  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Placeholder
|----------------------------------------------------------------------------*/

.jp-Placeholder {
  display: flex;
  flex-direction: row;
  flex: 1 1 auto;
}

.jp-Placeholder-prompt {
  box-sizing: border-box;
}

.jp-Placeholder-content {
  flex: 1 1 auto;
  border: none;
  background: transparent;
  height: 20px;
  box-sizing: border-box;
}

.jp-Placeholder-content .jp-MoreHorizIcon {
  width: 32px;
  height: 16px;
  border: 1px solid transparent;
  border-radius: var(--jp-border-radius);
}

.jp-Placeholder-content .jp-MoreHorizIcon:hover {
  border: 1px solid var(--jp-border-color1);
  box-shadow: 0px 0px 2px 0px rgba(0, 0, 0, 0.25);
  background-color: var(--jp-layout-color0);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-cell-scrolling-output-offset: 5px;
}

/*-----------------------------------------------------------------------------
| Cell
|----------------------------------------------------------------------------*/

.jp-Cell {
  padding: var(--jp-cell-padding);
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Common input/output
|----------------------------------------------------------------------------*/

.jp-Cell-inputWrapper,
.jp-Cell-outputWrapper {
  display: flex;
  flex-direction: row;
  padding: 0px;
  margin: 0px;
  /* Added to reveal the box-shadow on the input and output collapsers. */
  overflow: visible;
}

/* Only input/output areas inside cells */
.jp-Cell-inputArea,
.jp-Cell-outputArea {
  flex: 1 1 auto;
}

/*-----------------------------------------------------------------------------
| Collapser
|----------------------------------------------------------------------------*/

/* Make the output collapser disappear when there is not output, but do so
 * in a manner that leaves it in the layout and preserves its width.
 */
.jp-Cell.jp-mod-noOutputs .jp-Cell-outputCollapser {
  border: none !important;
  background: transparent !important;
}

.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputCollapser {
  min-height: var(--jp-cell-collapser-min-height);
}

/*-----------------------------------------------------------------------------
| Output
|----------------------------------------------------------------------------*/

/* Put a space between input and output when there IS output */
.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputWrapper {
  margin-top: 5px;
}

/* Text output with the Out[] prompt needs a top padding to match the
 * alignment of the Out[] prompt itself.
 */
.jp-OutputArea-executeResult .jp-RenderedText.jp-OutputArea-output {
  padding-top: var(--jp-code-padding);
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-Cell-outputArea {
  overflow-y: auto;
  max-height: 200px;
  box-shadow: inset 0 0 6px 2px rgba(0, 0, 0, 0.3);
  margin-left: var(--jp-private-cell-scrolling-output-offset);
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-prompt {
  flex: 0 0
    calc(
      var(--jp-cell-prompt-width) -
        var(--jp-private-cell-scrolling-output-offset)
    );
}

/*-----------------------------------------------------------------------------
| CodeCell
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| MarkdownCell
|----------------------------------------------------------------------------*/

.jp-MarkdownOutput {
  flex: 1 1 auto;
  margin-top: 0;
  margin-bottom: 0;
  padding-left: var(--jp-code-padding);
}

.jp-MarkdownOutput.jp-RenderedHTMLCommon {
  overflow: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------

/*-----------------------------------------------------------------------------
| Styles
|----------------------------------------------------------------------------*/

.jp-NotebookPanel-toolbar {
  padding: 2px;
}

.jp-Toolbar-item.jp-Notebook-toolbarCellType .jp-select-wrapper.jp-mod-focused {
  border: none;
  box-shadow: none;
}

.jp-Notebook-toolbarCellTypeDropdown select {
  height: 24px;
  font-size: var(--jp-ui-font-size1);
  line-height: 14px;
  border-radius: 0;
  display: block;
}

.jp-Notebook-toolbarCellTypeDropdown span {
  top: 5px !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-notebook-dragImage-width: 304px;
  --jp-private-notebook-dragImage-height: 36px;
  --jp-private-notebook-selected-color: var(--md-blue-400);
  --jp-private-notebook-active-color: var(--md-green-400);
}

/*-----------------------------------------------------------------------------
| Imports
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Notebook
|----------------------------------------------------------------------------*/

.jp-NotebookPanel {
  display: block;
  height: 100%;
}

.jp-NotebookPanel.jp-Document {
  min-width: 240px;
  min-height: 120px;
}

.jp-Notebook {
  padding: var(--jp-notebook-padding);
  outline: none;
  overflow: auto;
  background: var(--jp-layout-color0);
}

.jp-Notebook.jp-mod-scrollPastEnd::after {
  display: block;
  content: '';
  min-height: var(--jp-notebook-scroll-padding);
}

.jp-Notebook .jp-Cell {
  overflow: visible;
}

.jp-Notebook .jp-Cell .jp-InputPrompt {
  cursor: move;
}

/*-----------------------------------------------------------------------------
| Notebook state related styling
|
| The notebook and cells each have states, here are the possibilities:
|
| - Notebook
|   - Command
|   - Edit
| - Cell
|   - None
|   - Active (only one can be active)
|   - Selected (the cells actions are applied to)
|   - Multiselected (when multiple selected, the cursor)
|   - No outputs
|----------------------------------------------------------------------------*/

/* Command or edit modes */

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-InputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-OutputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

/* cell is active */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser {
  background: var(--jp-brand-color1);
}

/* collapser is hovered */
.jp-Notebook .jp-Cell .jp-Collapser:hover {
  box-shadow: var(--jp-elevation-z2);
  background: var(--jp-brand-color1);
  opacity: var(--jp-cell-collapser-not-active-hover-opacity);
}

/* cell is active and collapser is hovered */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser:hover {
  background: var(--jp-brand-color0);
  opacity: 1;
}

/* Command mode */

.jp-Notebook.jp-mod-commandMode .jp-Cell.jp-mod-selected {
  background: var(--jp-notebook-multiselected-color);
}

.jp-Notebook.jp-mod-commandMode
  .jp-Cell.jp-mod-active.jp-mod-selected:not(.jp-mod-multiSelected) {
  background: transparent;
}

/* Edit mode */

.jp-Notebook.jp-mod-editMode .jp-Cell.jp-mod-active .jp-InputArea-editor {
  border: var(--jp-border-width) solid var(--jp-cell-editor-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-cell-editor-active-background);
}

/*-----------------------------------------------------------------------------
| Notebook drag and drop
|----------------------------------------------------------------------------*/

.jp-Notebook-cell.jp-mod-dropSource {
  opacity: 0.5;
}

.jp-Notebook-cell.jp-mod-dropTarget,
.jp-Notebook.jp-mod-commandMode
  .jp-Notebook-cell.jp-mod-active.jp-mod-selected.jp-mod-dropTarget {
  border-top-color: var(--jp-private-notebook-selected-color);
  border-top-style: solid;
  border-top-width: 2px;
}

.jp-dragImage {
  display: flex;
  flex-direction: row;
  width: var(--jp-private-notebook-dragImage-width);
  height: var(--jp-private-notebook-dragImage-height);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background);
  overflow: visible;
}

.jp-dragImage-singlePrompt {
  box-shadow: 2px 2px 4px 0px rgba(0, 0, 0, 0.12);
}

.jp-dragImage .jp-dragImage-content {
  flex: 1 1 auto;
  z-index: 2;
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  line-height: var(--jp-code-line-height);
  padding: var(--jp-code-padding);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background-color);
  color: var(--jp-content-font-color3);
  text-align: left;
  margin: 4px 4px 4px 0px;
}

.jp-dragImage .jp-dragImage-prompt {
  flex: 0 0 auto;
  min-width: 36px;
  color: var(--jp-cell-inprompt-font-color);
  padding: var(--jp-code-padding);
  padding-left: 12px;
  font-family: var(--jp-cell-prompt-font-family);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: 1.9;
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
}

.jp-dragImage-multipleBack {
  z-index: -1;
  position: absolute;
  height: 32px;
  width: 300px;
  top: 8px;
  left: 8px;
  background: var(--jp-layout-color2);
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  box-shadow: 2px 2px 4px 0px rgba(0, 0, 0, 0.12);
}

/*-----------------------------------------------------------------------------
| Cell toolbar
|----------------------------------------------------------------------------*/

.jp-NotebookTools {
  display: block;
  min-width: var(--jp-sidebar-min-width);
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
    * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  overflow: auto;
}

.jp-NotebookTools-tool {
  padding: 0px 12px 0 12px;
}

.jp-ActiveCellTool {
  padding: 12px;
  background-color: var(--jp-layout-color1);
  border-top: none !important;
}

.jp-ActiveCellTool .jp-InputArea-prompt {
  flex: 0 0 auto;
  padding-left: 0px;
}

.jp-ActiveCellTool .jp-InputArea-editor {
  flex: 1 1 auto;
  background: var(--jp-cell-editor-background);
  border-color: var(--jp-cell-editor-border-color);
}

.jp-ActiveCellTool .jp-InputArea-editor .CodeMirror {
  background: transparent;
}

.jp-MetadataEditorTool {
  flex-direction: column;
  padding: 12px 0px 12px 0px;
}

.jp-RankedPanel > :not(:first-child) {
  margin-top: 12px;
}

.jp-KeySelector select.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: var(--jp-border-width) solid var(--jp-border-color1);
}

.jp-KeySelector label,
.jp-MetadataEditorTool label {
  line-height: 1.4;
}

/*-----------------------------------------------------------------------------
| Presentation Mode (.jp-mod-presentationMode)
|----------------------------------------------------------------------------*/

.jp-mod-presentationMode .jp-Notebook {
  --jp-content-font-size1: var(--jp-content-presentation-font-size1);
  --jp-code-font-size: var(--jp-code-presentation-font-size);
}

.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-InputPrompt,
.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-OutputPrompt {
  flex: 0 0 110px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

</style>

    <style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
The following CSS variables define the main, public API for styling JupyterLab.
These variables should be used by all plugins wherever possible. In other
words, plugins should not define custom colors, sizes, etc unless absolutely
necessary. This enables users to change the visual theme of JupyterLab
by changing these variables.

Many variables appear in an ordered sequence (0,1,2,3). These sequences
are designed to work well together, so for example, `--jp-border-color1` should
be used with `--jp-layout-color1`. The numbers have the following meanings:

* 0: super-primary, reserved for special emphasis
* 1: primary, most important under normal situations
* 2: secondary, next most important under normal situations
* 3: tertiary, next most important under normal situations

Throughout JupyterLab, we are mostly following principles from Google's
Material Design when selecting colors. We are not, however, following
all of MD as it is not optimized for dense, information rich UIs.
*/

:root {
  /* Elevation
   *
   * We style box-shadows using Material Design's idea of elevation. These particular numbers are taken from here:
   *
   * https://github.com/material-components/material-components-web
   * https://material-components-web.appspot.com/elevation.html
   */

  --jp-shadow-base-lightness: 0;
  --jp-shadow-umbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.2
  );
  --jp-shadow-penumbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.14
  );
  --jp-shadow-ambient-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.12
  );
  --jp-elevation-z0: none;
  --jp-elevation-z1: 0px 2px 1px -1px var(--jp-shadow-umbra-color),
    0px 1px 1px 0px var(--jp-shadow-penumbra-color),
    0px 1px 3px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z2: 0px 3px 1px -2px var(--jp-shadow-umbra-color),
    0px 2px 2px 0px var(--jp-shadow-penumbra-color),
    0px 1px 5px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z4: 0px 2px 4px -1px var(--jp-shadow-umbra-color),
    0px 4px 5px 0px var(--jp-shadow-penumbra-color),
    0px 1px 10px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z6: 0px 3px 5px -1px var(--jp-shadow-umbra-color),
    0px 6px 10px 0px var(--jp-shadow-penumbra-color),
    0px 1px 18px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z8: 0px 5px 5px -3px var(--jp-shadow-umbra-color),
    0px 8px 10px 1px var(--jp-shadow-penumbra-color),
    0px 3px 14px 2px var(--jp-shadow-ambient-color);
  --jp-elevation-z12: 0px 7px 8px -4px var(--jp-shadow-umbra-color),
    0px 12px 17px 2px var(--jp-shadow-penumbra-color),
    0px 5px 22px 4px var(--jp-shadow-ambient-color);
  --jp-elevation-z16: 0px 8px 10px -5px var(--jp-shadow-umbra-color),
    0px 16px 24px 2px var(--jp-shadow-penumbra-color),
    0px 6px 30px 5px var(--jp-shadow-ambient-color);
  --jp-elevation-z20: 0px 10px 13px -6px var(--jp-shadow-umbra-color),
    0px 20px 31px 3px var(--jp-shadow-penumbra-color),
    0px 8px 38px 7px var(--jp-shadow-ambient-color);
  --jp-elevation-z24: 0px 11px 15px -7px var(--jp-shadow-umbra-color),
    0px 24px 38px 3px var(--jp-shadow-penumbra-color),
    0px 9px 46px 8px var(--jp-shadow-ambient-color);

  /* Borders
   *
   * The following variables, specify the visual styling of borders in JupyterLab.
   */

  --jp-border-width: 1px;
  --jp-border-color0: var(--md-grey-400);
  --jp-border-color1: var(--md-grey-400);
  --jp-border-color2: var(--md-grey-300);
  --jp-border-color3: var(--md-grey-200);
  --jp-border-radius: 2px;

  /* UI Fonts
   *
   * The UI font CSS variables are used for the typography all of the JupyterLab
   * user interface elements that are not directly user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-ui-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-ui-font-scale-factor: 1.2;
  --jp-ui-font-size0: 0.83333em;
  --jp-ui-font-size1: 13px; /* Base font size */
  --jp-ui-font-size2: 1.2em;
  --jp-ui-font-size3: 1.44em;

  --jp-ui-font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica,
    Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol';

  /*
   * Use these font colors against the corresponding main layout colors.
   * In a light theme, these go from dark to light.
   */

  /* Defaults use Material Design specification */
  --jp-ui-font-color0: rgba(0, 0, 0, 1);
  --jp-ui-font-color1: rgba(0, 0, 0, 0.87);
  --jp-ui-font-color2: rgba(0, 0, 0, 0.54);
  --jp-ui-font-color3: rgba(0, 0, 0, 0.38);

  /*
   * Use these against the brand/accent/warn/error colors.
   * These will typically go from light to darker, in both a dark and light theme.
   */

  --jp-ui-inverse-font-color0: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color1: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color2: rgba(255, 255, 255, 0.7);
  --jp-ui-inverse-font-color3: rgba(255, 255, 255, 0.5);

  /* Content Fonts
   *
   * Content font variables are used for typography of user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-content-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-content-line-height: 1.6;
  --jp-content-font-scale-factor: 1.2;
  --jp-content-font-size0: 0.83333em;
  --jp-content-font-size1: 14px; /* Base font size */
  --jp-content-font-size2: 1.2em;
  --jp-content-font-size3: 1.44em;
  --jp-content-font-size4: 1.728em;
  --jp-content-font-size5: 2.0736em;

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-content-presentation-font-size1: 17px;

  --jp-content-heading-line-height: 1;
  --jp-content-heading-margin-top: 1.2em;
  --jp-content-heading-margin-bottom: 0.8em;
  --jp-content-heading-font-weight: 500;

  /* Defaults use Material Design specification */
  --jp-content-font-color0: rgba(0, 0, 0, 1);
  --jp-content-font-color1: rgba(0, 0, 0, 0.87);
  --jp-content-font-color2: rgba(0, 0, 0, 0.54);
  --jp-content-font-color3: rgba(0, 0, 0, 0.38);

  --jp-content-link-color: var(--md-blue-700);

  --jp-content-font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji',
    'Segoe UI Symbol';

  /*
   * Code Fonts
   *
   * Code font variables are used for typography of code and other monospaces content.
   */

  --jp-code-font-size: 13px;
  --jp-code-line-height: 1.3077; /* 17px for 13px base */
  --jp-code-padding: 5px; /* 5px for 13px base, codemirror highlighting needs integer px value */
  --jp-code-font-family-default: Menlo, Consolas, 'DejaVu Sans Mono', monospace;
  --jp-code-font-family: var(--jp-code-font-family-default);

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-code-presentation-font-size: 16px;

  /* may need to tweak cursor width if you change font size */
  --jp-code-cursor-width0: 1.4px;
  --jp-code-cursor-width1: 2px;
  --jp-code-cursor-width2: 4px;

  /* Layout
   *
   * The following are the main layout colors use in JupyterLab. In a light
   * theme these would go from light to dark.
   */

  --jp-layout-color0: white;
  --jp-layout-color1: white;
  --jp-layout-color2: var(--md-grey-200);
  --jp-layout-color3: var(--md-grey-400);
  --jp-layout-color4: var(--md-grey-600);

  /* Inverse Layout
   *
   * The following are the inverse layout colors use in JupyterLab. In a light
   * theme these would go from dark to light.
   */

  --jp-inverse-layout-color0: #111111;
  --jp-inverse-layout-color1: var(--md-grey-900);
  --jp-inverse-layout-color2: var(--md-grey-800);
  --jp-inverse-layout-color3: var(--md-grey-700);
  --jp-inverse-layout-color4: var(--md-grey-600);

  /* Brand/accent */

  --jp-brand-color0: var(--md-blue-700);
  --jp-brand-color1: var(--md-blue-500);
  --jp-brand-color2: var(--md-blue-300);
  --jp-brand-color3: var(--md-blue-100);
  --jp-brand-color4: var(--md-blue-50);

  --jp-accent-color0: var(--md-green-700);
  --jp-accent-color1: var(--md-green-500);
  --jp-accent-color2: var(--md-green-300);
  --jp-accent-color3: var(--md-green-100);

  /* State colors (warn, error, success, info) */

  --jp-warn-color0: var(--md-orange-700);
  --jp-warn-color1: var(--md-orange-500);
  --jp-warn-color2: var(--md-orange-300);
  --jp-warn-color3: var(--md-orange-100);

  --jp-error-color0: var(--md-red-700);
  --jp-error-color1: var(--md-red-500);
  --jp-error-color2: var(--md-red-300);
  --jp-error-color3: var(--md-red-100);

  --jp-success-color0: var(--md-green-700);
  --jp-success-color1: var(--md-green-500);
  --jp-success-color2: var(--md-green-300);
  --jp-success-color3: var(--md-green-100);

  --jp-info-color0: var(--md-cyan-700);
  --jp-info-color1: var(--md-cyan-500);
  --jp-info-color2: var(--md-cyan-300);
  --jp-info-color3: var(--md-cyan-100);

  /* Cell specific styles */

  --jp-cell-padding: 5px;

  --jp-cell-collapser-width: 8px;
  --jp-cell-collapser-min-height: 20px;
  --jp-cell-collapser-not-active-hover-opacity: 0.6;

  --jp-cell-editor-background: var(--md-grey-100);
  --jp-cell-editor-border-color: var(--md-grey-300);
  --jp-cell-editor-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-cell-editor-active-background: var(--jp-layout-color0);
  --jp-cell-editor-active-border-color: var(--jp-brand-color1);

  --jp-cell-prompt-width: 64px;
  --jp-cell-prompt-font-family: 'Source Code Pro', monospace;
  --jp-cell-prompt-letter-spacing: 0px;
  --jp-cell-prompt-opacity: 1;
  --jp-cell-prompt-not-active-opacity: 0.5;
  --jp-cell-prompt-not-active-font-color: var(--md-grey-700);
  /* A custom blend of MD grey and blue 600
   * See https://meyerweb.com/eric/tools/color-blend/#546E7A:1E88E5:5:hex */
  --jp-cell-inprompt-font-color: #307fc1;
  /* A custom blend of MD grey and orange 600
   * https://meyerweb.com/eric/tools/color-blend/#546E7A:F4511E:5:hex */
  --jp-cell-outprompt-font-color: #bf5b3d;

  /* Notebook specific styles */

  --jp-notebook-padding: 10px;
  --jp-notebook-select-background: var(--jp-layout-color1);
  --jp-notebook-multiselected-color: var(--md-blue-50);

  /* The scroll padding is calculated to fill enough space at the bottom of the
  notebook to show one single-line cell (with appropriate padding) at the top
  when the notebook is scrolled all the way to the bottom. We also subtract one
  pixel so that no scrollbar appears if we have just one single-line cell in the
  notebook. This padding is to enable a 'scroll past end' feature in a notebook.
  */
  --jp-notebook-scroll-padding: calc(
    100% - var(--jp-code-font-size) * var(--jp-code-line-height) -
      var(--jp-code-padding) - var(--jp-cell-padding) - 1px
  );

  /* Rendermime styles */

  --jp-rendermime-error-background: #fdd;
  --jp-rendermime-table-row-background: var(--md-grey-100);
  --jp-rendermime-table-row-hover-background: var(--md-light-blue-50);

  /* Dialog specific styles */

  --jp-dialog-background: rgba(0, 0, 0, 0.25);

  /* Console specific styles */

  --jp-console-padding: 10px;

  /* Toolbar specific styles */

  --jp-toolbar-border-color: var(--jp-border-color1);
  --jp-toolbar-micro-height: 8px;
  --jp-toolbar-background: var(--jp-layout-color1);
  --jp-toolbar-box-shadow: 0px 0px 2px 0px rgba(0, 0, 0, 0.24);
  --jp-toolbar-header-margin: 4px 4px 0px 4px;
  --jp-toolbar-active-background: var(--md-grey-300);

  /* Input field styles */

  --jp-input-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-input-active-background: var(--jp-layout-color1);
  --jp-input-hover-background: var(--jp-layout-color1);
  --jp-input-background: var(--md-grey-100);
  --jp-input-border-color: var(--jp-border-color1);
  --jp-input-active-border-color: var(--jp-brand-color1);
  --jp-input-active-box-shadow-color: rgba(19, 124, 189, 0.3);

  /* General editor styles */

  --jp-editor-selected-background: #d9d9d9;
  --jp-editor-selected-focused-background: #d7d4f0;
  --jp-editor-cursor-color: var(--jp-ui-font-color0);

  /* Code mirror specific styles */

  --jp-mirror-editor-keyword-color: #008000;
  --jp-mirror-editor-atom-color: #88f;
  --jp-mirror-editor-number-color: #080;
  --jp-mirror-editor-def-color: #00f;
  --jp-mirror-editor-variable-color: var(--md-grey-900);
  --jp-mirror-editor-variable-2-color: #05a;
  --jp-mirror-editor-variable-3-color: #085;
  --jp-mirror-editor-punctuation-color: #05a;
  --jp-mirror-editor-property-color: #05a;
  --jp-mirror-editor-operator-color: #aa22ff;
  --jp-mirror-editor-comment-color: #408080;
  --jp-mirror-editor-string-color: #ba2121;
  --jp-mirror-editor-string-2-color: #708;
  --jp-mirror-editor-meta-color: #aa22ff;
  --jp-mirror-editor-qualifier-color: #555;
  --jp-mirror-editor-builtin-color: #008000;
  --jp-mirror-editor-bracket-color: #997;
  --jp-mirror-editor-tag-color: #170;
  --jp-mirror-editor-attribute-color: #00c;
  --jp-mirror-editor-header-color: blue;
  --jp-mirror-editor-quote-color: #090;
  --jp-mirror-editor-link-color: #00c;
  --jp-mirror-editor-error-color: #f00;
  --jp-mirror-editor-hr-color: #999;

  /* Vega extension styles */

  --jp-vega-background: white;

  /* Sidebar-related styles */

  --jp-sidebar-min-width: 180px;

  /* Search-related styles */

  --jp-search-toggle-off-opacity: 0.5;
  --jp-search-toggle-hover-opacity: 0.8;
  --jp-search-toggle-on-opacity: 1;
  --jp-search-selected-match-background-color: rgb(245, 200, 0);
  --jp-search-selected-match-color: black;
  --jp-search-unselected-match-background-color: var(
    --jp-inverse-layout-color0
  );
  --jp-search-unselected-match-color: var(--jp-ui-inverse-font-color0);

  /* Icon colors that work well with light or dark backgrounds */
  --jp-icon-contrast-color0: var(--md-purple-600);
  --jp-icon-contrast-color1: var(--md-green-600);
  --jp-icon-contrast-color2: var(--md-pink-600);
  --jp-icon-contrast-color3: var(--md-blue-600);
}
</style>

<style type="text/css">
a.anchor-link {
   display: none;
}
.highlight  {
    margin: 0.4em;
}

/* Input area styling */
.jp-InputArea {
    overflow: hidden;
}

.jp-InputArea-editor {
    overflow: hidden;
}

@media print {
  body {
    margin: 0;
  }
}
</style>



<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/latest.js?config=TeX-MML-AM_CHTML-full,Safe"> </script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    init_mathjax = function() {
        if (window.MathJax) {
        // MathJax loaded
            MathJax.Hub.Config({
                TeX: {
                    equationNumbers: {
                    autoNumber: "AMS",
                    useLabelIds: true
                    }
                },
                tex2jax: {
                    inlineMath: [ ['$','$'], ["\\(","\\)"] ],
                    displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
                    processEscapes: true,
                    processEnvironments: true
                },
                displayAlign: 'center',
                CommonHTML: {
                    linebreaks: { 
                    automatic: true 
                    }
                },
                "HTML-CSS": {
                    linebreaks: { 
                    automatic: true 
                    }
                }
            });
        
            MathJax.Hub.Queue(["Typeset", MathJax.Hub]);
        }
    }
    init_mathjax();
    </script>
    <!-- End of mathjax configuration --></head>
<body class="jp-Notebook" data-jp-theme-light="true" data-jp-theme-name="JupyterLab Light">
<div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[1]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">json</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">from</span> <span class="nn">numpy.lib.index_tricks</span> <span class="kn">import</span> <span class="n">AxisConcatenator</span>


<span class="k">class</span> <span class="nc">Restaurants</span><span class="p">:</span>

    <span class="n">headers</span> <span class="o">=</span> <span class="p">[</span>
        <span class="s2">&quot;Name&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Location&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Stars&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Review Count&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Dogs Allowed&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Bike Parking&quot;</span><span class="p">,</span>
    <span class="p">]</span>

    <span class="n">cuisines</span> <span class="o">=</span> <span class="p">[</span>
        <span class="s2">&quot;American&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Burgers&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Fast Food&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Coffee&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Bars&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Nightlife&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Breweries&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Italian&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Chinese&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Asian Fusion&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Korean&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Japanese&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Sushi&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Thai&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Pizza&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Soup&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Salad&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Delis&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Food Truck&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Street&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Seafood&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Veg&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Indian&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Ice Cream&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Tacos&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Mexican&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Bakeries&quot;</span><span class="p">,</span>
        <span class="s2">&quot;Sandwiches&quot;</span><span class="p">,</span>
    <span class="p">]</span>

    <span class="n">final_array</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">concatenate</span><span class="p">((</span><span class="n">headers</span><span class="p">,</span> <span class="n">cuisines</span><span class="p">),</span> <span class="n">axis</span><span class="o">=</span><span class="kc">None</span><span class="p">)</span>

    <span class="k">def</span> <span class="fm">__init__</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">data</span><span class="p">):</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">name</span> <span class="o">=</span> <span class="n">data</span><span class="p">[</span><span class="s2">&quot;name&quot;</span><span class="p">]</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">location</span> <span class="o">=</span> <span class="p">[</span><span class="n">data</span><span class="p">[</span><span class="s2">&quot;latitude&quot;</span><span class="p">],</span> <span class="n">data</span><span class="p">[</span><span class="s2">&quot;longitude&quot;</span><span class="p">]]</span>  <span class="c1"># DEPRECATION WARNING</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">stars</span> <span class="o">=</span> <span class="n">data</span><span class="p">[</span><span class="s2">&quot;stars&quot;</span><span class="p">]</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">review_count</span> <span class="o">=</span> <span class="n">data</span><span class="p">[</span><span class="s2">&quot;review_count&quot;</span><span class="p">]</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">dogs_allowed</span> <span class="o">=</span> <span class="mi">0</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">bike_parking</span> <span class="o">=</span> <span class="mi">0</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">temp_array</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">zeros</span><span class="p">(</span><span class="mi">6</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="nb">int</span><span class="p">)</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">temp_cuisines</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">zeros</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">Restaurants</span><span class="o">.</span><span class="n">cuisines</span><span class="p">),</span> <span class="n">dtype</span><span class="o">=</span><span class="nb">int</span><span class="p">)</span>

        <span class="k">if</span> <span class="n">data</span><span class="p">[</span><span class="s2">&quot;attributes&quot;</span><span class="p">]:</span>
            <span class="k">if</span> <span class="s2">&quot;DogsAllowed&quot;</span> <span class="ow">in</span> <span class="n">data</span><span class="p">[</span><span class="s2">&quot;attributes&quot;</span><span class="p">]:</span>
                <span class="k">if</span> <span class="n">data</span><span class="p">[</span><span class="s2">&quot;attributes&quot;</span><span class="p">][</span><span class="s2">&quot;DogsAllowed&quot;</span><span class="p">]</span> <span class="o">==</span> <span class="s2">&quot;True&quot;</span><span class="p">:</span>
                    <span class="bp">self</span><span class="o">.</span><span class="n">dogs_allowed</span> <span class="o">=</span> <span class="mi">1</span>
            <span class="k">if</span> <span class="s2">&quot;BikeParking&quot;</span> <span class="ow">in</span> <span class="n">data</span><span class="p">[</span><span class="s2">&quot;attributes&quot;</span><span class="p">]:</span>
                <span class="k">if</span> <span class="n">data</span><span class="p">[</span><span class="s2">&quot;attributes&quot;</span><span class="p">][</span><span class="s2">&quot;BikeParking&quot;</span><span class="p">]</span> <span class="o">==</span> <span class="s2">&quot;True&quot;</span><span class="p">:</span>
                    <span class="bp">self</span><span class="o">.</span><span class="n">bike_parking</span> <span class="o">=</span> <span class="mi">1</span>

        <span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">Restaurants</span><span class="o">.</span><span class="n">cuisines</span><span class="p">)):</span>
            <span class="k">if</span> <span class="n">Restaurants</span><span class="o">.</span><span class="n">cuisines</span><span class="p">[</span><span class="n">i</span><span class="p">]</span> <span class="ow">in</span> <span class="n">data</span><span class="p">[</span><span class="s2">&quot;categories&quot;</span><span class="p">]:</span>
                <span class="bp">self</span><span class="o">.</span><span class="n">temp_cuisines</span><span class="p">[</span><span class="n">i</span><span class="p">]</span> <span class="o">=</span> <span class="mi">1</span>

        <span class="bp">self</span><span class="o">.</span><span class="n">temp_array</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">(</span>
            <span class="p">[</span>
                <span class="bp">self</span><span class="o">.</span><span class="n">name</span><span class="p">,</span>
                <span class="bp">self</span><span class="o">.</span><span class="n">location</span><span class="p">,</span>
                <span class="bp">self</span><span class="o">.</span><span class="n">stars</span><span class="p">,</span>
                <span class="bp">self</span><span class="o">.</span><span class="n">review_count</span><span class="p">,</span>
                <span class="bp">self</span><span class="o">.</span><span class="n">dogs_allowed</span><span class="p">,</span>
                <span class="bp">self</span><span class="o">.</span><span class="n">bike_parking</span><span class="p">,</span>
            <span class="p">]</span>
        <span class="p">)</span>
        <span class="n">new_row</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">concatenate</span><span class="p">((</span><span class="bp">self</span><span class="o">.</span><span class="n">temp_array</span><span class="p">,</span> <span class="bp">self</span><span class="o">.</span><span class="n">temp_cuisines</span><span class="p">),</span> <span class="n">axis</span><span class="o">=</span><span class="kc">None</span><span class="p">)</span>

        <span class="n">Restaurants</span><span class="o">.</span><span class="n">final_array</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">vstack</span><span class="p">((</span><span class="n">Restaurants</span><span class="o">.</span><span class="n">final_array</span><span class="p">,</span> <span class="n">new_row</span><span class="p">))</span>


<span class="k">def</span> <span class="nf">main</span><span class="p">():</span>

    <span class="k">with</span> <span class="nb">open</span><span class="p">(</span><span class="s2">&quot;yelp_academic_dataset_business.json&quot;</span><span class="p">)</span> <span class="k">as</span> <span class="n">f</span><span class="p">:</span>
        <span class="k">for</span> <span class="n">line</span> <span class="ow">in</span> <span class="n">f</span><span class="p">:</span>
            <span class="n">data</span> <span class="o">=</span> <span class="n">json</span><span class="o">.</span><span class="n">loads</span><span class="p">(</span><span class="n">line</span><span class="p">)</span>

            <span class="k">if</span> <span class="p">(</span>
                <span class="n">data</span><span class="p">[</span><span class="s2">&quot;city&quot;</span><span class="p">]</span> <span class="o">==</span> <span class="s2">&quot;Portland&quot;</span>
                <span class="ow">and</span> <span class="n">data</span><span class="p">[</span><span class="s2">&quot;is_open&quot;</span><span class="p">]</span> <span class="o">==</span> <span class="mi">1</span>
                <span class="ow">and</span> <span class="n">data</span><span class="p">[</span><span class="s2">&quot;categories&quot;</span><span class="p">]</span>
            <span class="p">):</span>

                <span class="k">if</span> <span class="p">(</span>
                    <span class="s2">&quot;Restaurants&quot;</span> <span class="ow">in</span> <span class="n">data</span><span class="p">[</span><span class="s2">&quot;categories&quot;</span><span class="p">]</span>
                    <span class="ow">or</span> <span class="s2">&quot;Restaurant&quot;</span> <span class="ow">in</span> <span class="n">data</span><span class="p">[</span><span class="s2">&quot;categories&quot;</span><span class="p">]</span>
                    <span class="ow">or</span> <span class="s2">&quot;restaurants&quot;</span> <span class="ow">in</span> <span class="n">data</span><span class="p">[</span><span class="s2">&quot;categories&quot;</span><span class="p">]</span>
                    <span class="ow">or</span> <span class="s2">&quot;restaurant&quot;</span> <span class="ow">in</span> <span class="n">data</span><span class="p">[</span><span class="s2">&quot;categories&quot;</span><span class="p">]</span>
                <span class="p">):</span>
                    <span class="n">x</span> <span class="o">=</span> <span class="n">Restaurants</span><span class="p">(</span><span class="n">data</span><span class="p">)</span>

        <span class="n">np</span><span class="o">.</span><span class="n">savetxt</span><span class="p">(</span><span class="s2">&quot;foo.csv&quot;</span><span class="p">,</span> <span class="n">Restaurants</span><span class="o">.</span><span class="n">final_array</span><span class="p">,</span> <span class="n">delimiter</span><span class="o">=</span><span class="s2">&quot;,&quot;</span><span class="p">,</span> <span class="n">fmt</span><span class="o">=</span><span class="s2">&quot;</span><span class="si">%s</span><span class="s2">&quot;</span><span class="p">)</span>


<span class="n">main</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="application/vnd.jupyter.stderr">
<pre>&lt;ipython-input-1-0ba3b89b0994&gt;:72: VisibleDeprecationWarning: Creating an ndarray from ragged nested sequences (which is a list-or-tuple of lists-or-tuples-or ndarrays with different lengths or shapes) is deprecated. If you meant to do this, you must specify &#39;dtype=object&#39; when creating the ndarray.
  self.temp_array = np.array(
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[2]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sns</span>
<span class="kn">import</span> <span class="nn">geopandas</span> <span class="k">as</span> <span class="nn">gpd</span>
<span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">folium</span>
<span class="kn">from</span> <span class="nn">folium.plugins</span> <span class="kn">import</span> <span class="n">HeatMap</span>

<span class="n">df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s2">&quot;cleaned_table_2.csv&quot;</span><span class="p">,</span> <span class="n">header</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>

<span class="c1"># Clean the GPS coordinate data; removing characters</span>
<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">df</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="n">df</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s2">&quot;Latitude&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="n">row</span><span class="p">[</span><span class="s2">&quot;Latitude&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="s2">&quot;[&quot;</span><span class="p">,</span> <span class="s2">&quot;&quot;</span><span class="p">)</span>

<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">df</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="n">df</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s2">&quot;Longitude&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="n">row</span><span class="p">[</span><span class="s2">&quot;Longitude&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="s2">&quot;]&quot;</span><span class="p">,</span> <span class="s2">&quot;&quot;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[3]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>

<span class="c1"># See which columns are highly correlated/redundant.</span>
<span class="c1"># Will combine and remove redundant columns</span>

<span class="n">corr_matrix</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">corr</span><span class="p">()</span><span class="o">.</span><span class="n">abs</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">matshow</span><span class="p">(</span><span class="n">df</span><span class="o">.</span><span class="n">corr</span><span class="p">()</span><span class="o">.</span><span class="n">abs</span><span class="p">())</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>

<span class="c1"># Deprecation Warning</span>
<span class="n">sol</span> <span class="o">=</span> <span class="p">(</span>
    <span class="n">corr_matrix</span><span class="o">.</span><span class="n">where</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">triu</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">ones</span><span class="p">(</span><span class="n">corr_matrix</span><span class="o">.</span><span class="n">shape</span><span class="p">),</span> <span class="n">k</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">bool</span><span class="p">))</span>
    <span class="o">.</span><span class="n">stack</span><span class="p">()</span>
    <span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="n">ascending</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>
<span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="application/vnd.jupyter.stderr">
<pre>&lt;ipython-input-3-fcbabb8de90b&gt;:12: DeprecationWarning: `np.bool` is a deprecated alias for the builtin `bool`. To silence this warning, use `bool` by itself. Doing this will not modify any behavior and is safe. If you specifically wanted the numpy scalar type, use `np.bool_` here.
Deprecated in NumPy 1.20; for more details and guidance: https://numpy.org/devdocs/release/1.20.0-notes.html#deprecations
  corr_matrix.where(np.triu(np.ones(corr_matrix.shape), k=1).astype(np.bool))
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[4]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">value</span> <span class="ow">in</span> <span class="n">sol</span><span class="o">.</span><span class="n">items</span><span class="p">():</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">index</span><span class="p">,</span> <span class="n">value</span><span class="p">)</span>

<span class="c1">#  We see that Bars+Nightlife , Japanese + Sushi, Tacos + Mexican correlate and are redundant</span>
<span class="c1"># Let&#39;s combine those colum pairs, and drop redundant columns</span>

<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">df</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="k">if</span> <span class="n">row</span><span class="p">[</span><span class="s2">&quot;Bars&quot;</span><span class="p">]</span> <span class="o">==</span> <span class="mi">1</span> <span class="ow">or</span> <span class="n">row</span><span class="p">[</span><span class="s2">&quot;Nightlife&quot;</span><span class="p">]</span> <span class="o">==</span> <span class="mi">1</span><span class="p">:</span>
        <span class="n">df</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s2">&quot;Bars&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="mi">1</span>
<span class="n">df</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s2">&quot;Nightlife&quot;</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>

<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">df</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="k">if</span> <span class="n">row</span><span class="p">[</span><span class="s2">&quot;Japanese&quot;</span><span class="p">]</span> <span class="o">==</span> <span class="mi">1</span> <span class="ow">or</span> <span class="n">row</span><span class="p">[</span><span class="s2">&quot;Sushi&quot;</span><span class="p">]</span> <span class="o">==</span> <span class="mi">1</span><span class="p">:</span>
        <span class="n">df</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s2">&quot;Japanese&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="mi">1</span>
<span class="n">df</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s2">&quot;Sushi&quot;</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>

<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">df</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="k">if</span> <span class="n">row</span><span class="p">[</span><span class="s2">&quot;Mexican&quot;</span><span class="p">]</span> <span class="o">==</span> <span class="mi">1</span> <span class="ow">or</span> <span class="n">row</span><span class="p">[</span><span class="s2">&quot;Tacos&quot;</span><span class="p">]</span> <span class="o">==</span> <span class="mi">1</span><span class="p">:</span>
        <span class="n">df</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s2">&quot;Mexican&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="mi">1</span>
<span class="n">df</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s2">&quot;Tacos&quot;</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>

<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">df</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="k">if</span> <span class="n">row</span><span class="p">[</span><span class="s2">&quot;Food Truck&quot;</span><span class="p">]</span> <span class="o">==</span> <span class="mi">1</span> <span class="ow">or</span> <span class="n">row</span><span class="p">[</span><span class="s2">&quot;Street&quot;</span><span class="p">]</span> <span class="o">==</span> <span class="mi">1</span><span class="p">:</span>
        <span class="n">df</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s2">&quot;Street&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="mi">1</span>
<span class="n">df</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s2">&quot;Food Truck&quot;</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>(&#39;Bars&#39;, &#39;Nightlife&#39;) 0.8488083494661861
(&#39;Japanese&#39;, &#39;Sushi&#39;) 0.6031089444282572
(&#39;Stars&#39;, &#39;Fast Food&#39;) 0.45143855806153915
(&#39;Tacos&#39;, &#39;Mexican&#39;) 0.40323978565112895
(&#39;American&#39;, &#39;Nightlife&#39;) 0.3784129432665705
(&#39;American&#39;, &#39;Bars&#39;) 0.32368537085728494
(&#39;Bars&#39;, &#39;Sushi&#39;) 0.29245120557515464
(&#39;Burgers&#39;, &#39;Fast Food&#39;) 0.2884957990586375
(&#39;Italian&#39;, &#39;Pizza&#39;) 0.28033449984047987
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[5]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df2</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">select_dtypes</span><span class="p">(</span><span class="n">include</span><span class="o">=</span><span class="s2">&quot;int&quot;</span><span class="p">)</span>
<span class="n">df2</span> <span class="o">=</span> <span class="n">df2</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s2">&quot;Review Count&quot;</span><span class="p">,</span> <span class="s2">&quot;Dogs Allowed&quot;</span><span class="p">,</span> <span class="s2">&quot;Bike Parking&quot;</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="n">df2</span> <span class="o">=</span> <span class="n">df2</span><span class="o">.</span><span class="n">join</span><span class="p">(</span><span class="n">df</span><span class="p">[</span><span class="s2">&quot;Stars&quot;</span><span class="p">])</span>

<span class="n">true_columns</span> <span class="o">=</span> <span class="p">[]</span>


<span class="c1"># Parsing and recasting data in a new dataframe to match format for the Seaborn plot</span>
<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">df2</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="k">for</span> <span class="n">col</span> <span class="ow">in</span> <span class="n">df2</span><span class="p">:</span>
        <span class="k">if</span> <span class="n">row</span><span class="p">[</span><span class="n">col</span><span class="p">]</span> <span class="o">==</span> <span class="mi">1</span><span class="p">:</span>
            <span class="n">true_columns</span> <span class="o">+=</span> <span class="p">[</span><span class="n">col</span><span class="p">,</span> <span class="n">row</span><span class="p">[</span><span class="o">-</span><span class="mi">1</span><span class="p">]]</span>

<span class="n">true_columns</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">asarray</span><span class="p">(</span><span class="n">true_columns</span><span class="p">)</span>
<span class="n">true_columns</span> <span class="o">=</span> <span class="n">true_columns</span><span class="o">.</span><span class="n">reshape</span><span class="p">(</span><span class="o">-</span><span class="mi">1</span><span class="p">,</span> <span class="mi">2</span><span class="p">)</span>
<span class="n">df3</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">(</span><span class="n">true_columns</span><span class="p">,</span> <span class="n">columns</span><span class="o">=</span><span class="p">[</span><span class="s2">&quot;Cuisine&quot;</span><span class="p">,</span> <span class="s2">&quot;Stars&quot;</span><span class="p">])</span>

<span class="c1"># Readding &quot;stars&quot;, which is the y-axis in the Seaborn plot</span>
<span class="n">df3</span><span class="p">[</span><span class="s2">&quot;Stars&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="s2">&quot;Stars&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="nb">float</span><span class="p">)</span>
<span class="n">df3</span> <span class="o">=</span> <span class="n">df3</span><span class="p">[</span><span class="n">df3</span><span class="p">[</span><span class="s2">&quot;Cuisine&quot;</span><span class="p">]</span> <span class="o">!=</span> <span class="s2">&quot;Stars&quot;</span><span class="p">]</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[13]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">15</span><span class="p">,</span> <span class="mi">5</span><span class="p">))</span>
<span class="n">violins</span> <span class="o">=</span> <span class="n">sns</span><span class="o">.</span><span class="n">violinplot</span><span class="p">(</span>
    <span class="n">data</span><span class="o">=</span><span class="n">df3</span><span class="p">,</span>
    <span class="n">y</span><span class="o">=</span><span class="s2">&quot;Stars&quot;</span><span class="p">,</span>
    <span class="n">x</span><span class="o">=</span><span class="s2">&quot;Cuisine&quot;</span><span class="p">,</span>
    <span class="n">inner</span><span class="o">=</span><span class="kc">None</span><span class="p">,</span>
    <span class="n">linewidth</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>
    <span class="n">scale</span><span class="o">=</span><span class="s2">&quot;width&quot;</span><span class="p">,</span>
    <span class="n">palette</span><span class="o">=</span><span class="s2">&quot;magma&quot;</span><span class="p">,</span>
<span class="p">)</span>

<span class="n">violins</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="s2">&quot;Star Rating by Cuisine&quot;</span><span class="p">,</span> <span class="n">fontsize</span><span class="o">=</span><span class="mi">20</span><span class="p">)</span>
<span class="n">violins</span><span class="o">.</span><span class="n">set_ylabel</span><span class="p">(</span><span class="s2">&quot;&quot;</span><span class="p">)</span>
<span class="n">violins</span><span class="o">.</span><span class="n">set_xlabel</span><span class="p">(</span><span class="s2">&quot;&quot;</span><span class="p">)</span>
<span class="n">violins</span><span class="o">.</span><span class="n">set_yticklabels</span><span class="p">([</span><span class="s2">&quot;&quot;</span><span class="p">,</span> <span class="s2">&quot;1&quot;</span><span class="p">,</span> <span class="s2">&quot;2&quot;</span><span class="p">,</span> <span class="s2">&quot;3&quot;</span><span class="p">,</span> <span class="s2">&quot;4&quot;</span><span class="p">,</span> <span class="s2">&quot;5&quot;</span><span class="p">],</span> <span class="n">fontsize</span><span class="o">=</span><span class="mi">20</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xticks</span><span class="p">(</span><span class="n">rotation</span><span class="o">=</span><span class="mi">90</span><span class="p">,</span> <span class="n">fontsize</span><span class="o">=</span><span class="mi">20</span><span class="p">)</span>

<span class="n">plt</span><span class="o">.</span><span class="n">tight_layout</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">savefig</span><span class="p">(</span><span class="s2">&quot;ratings_chart.png&quot;</span><span class="p">,</span> <span class="n">dpi</span><span class="o">=</span><span class="mi">300</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="application/vnd.jupyter.stderr">
<pre>&lt;ipython-input-13-e1bf6bb2bae7&gt;:7: UserWarning: FixedFormatter should only be used together with FixedLocator
  violins.set_yticklabels([&#39;&#39;,&#39;1&#39;,&#39;2&#39;,&#39;3&#39;,&#39;4&#39;,&#39;5&#39;], fontsize = 20)
</pre>
</div>
</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[11]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">hmap</span> <span class="o">=</span> <span class="n">folium</span><span class="o">.</span><span class="n">Map</span><span class="p">(</span>
    <span class="n">location</span><span class="o">=</span><span class="p">[</span><span class="mf">45.5253094</span><span class="p">,</span> <span class="o">-</span><span class="mf">122.677018</span><span class="p">],</span>
    <span class="n">zoom_start</span><span class="o">=</span><span class="mi">13</span><span class="p">,</span>
<span class="p">)</span>

<span class="n">hm_wide</span> <span class="o">=</span> <span class="n">HeatMap</span><span class="p">(</span>
    <span class="nb">list</span><span class="p">(</span><span class="nb">zip</span><span class="p">(</span><span class="n">df</span><span class="o">.</span><span class="n">Latitude</span><span class="o">.</span><span class="n">values</span><span class="p">,</span> <span class="n">df</span><span class="o">.</span><span class="n">Longitude</span><span class="o">.</span><span class="n">values</span><span class="p">,</span> <span class="n">df</span><span class="o">.</span><span class="n">Stars</span><span class="o">.</span><span class="n">values</span><span class="p">)),</span>
    <span class="n">min_opacity</span><span class="o">=</span><span class="mf">0.3</span><span class="p">,</span>
    <span class="n">radius</span><span class="o">=</span><span class="mi">12</span><span class="p">,</span>
    <span class="n">blur</span><span class="o">=</span><span class="mi">12</span><span class="p">,</span>
    <span class="n">max_zoom</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span>
<span class="p">)</span>

<span class="n">hmap</span><span class="o">.</span><span class="n">add_child</span><span class="p">(</span><span class="n">hm_wide</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[11]:</div>



    <img src="githubmap.png" alt="Map">


</div>

</div>

</div>

</div>
</body>







</html>



    </main>
</div>
