---
created: Monday, December 5th 2022 - 13.44
updated: Monday, December 5th 2022 - 13.44
---
<div id="gfs6qaa4fod-instruction"><p>Create an Image class that supports image cloning. Multiple tools make&nbsp;copy-pasting&nbsp;images possible by cloning them.</p>

<p>&nbsp;</p>

<p>Implementation of class <em>Size&nbsp;</em>is already provided.</p>

<ol>
	<li>This class has a constructor <em>Size(width, height)</em> to set the width and height of the <em>Size</em> object created.</li>
</ol>

<p>&nbsp;</p>

<p>Implement the <em>Image</em>&nbsp;class with the following constructor and methods:</p>

<ol>
	<li>The constructor&nbsp;<em>Image(String url, Size&nbsp;size)&nbsp;</em>sets the url and size of the image object created.</li>
	<li>The method&nbsp;<em>getUrl()</em>&nbsp;returns the <em>url</em>.</li>
	<li>The method&nbsp;<em>setUrl(url)</em>&nbsp;updates the <em>url</em>.</li>
	<li>The method&nbsp;<em>setSize(width, height)</em>&nbsp;updates the <em>width</em> and <em>height</em> values of the size property.</li>
	<li>The method&nbsp;<em>getSize()</em>&nbsp;returns the size of the image&nbsp;as a&nbsp;<em>Size&nbsp;</em>object.</li>
	<li>The method&nbsp;<em>cloneImage()</em>&nbsp;returns a clone of the current image. Return a new <em>Image</em> instance&nbsp;with the same properties (<em>url</em> and <em>size</em>) as the current object.</li>
</ol>

<p>&nbsp;</p>

<p>The locked stub&nbsp;code validates the correctness of the <em>Image</em> class implementation by performing the following operations on the images:</p>

<ul>
	<li>
<em>Clone Id</em>: This operation creates a clone of the image.</li>
	<li>
<em>UpdateUrl Id newUrl</em>:&nbsp;This operation updates the <em>url</em> of the image.</li>
	<li>
<em>UpdateSize Id newWidth newHeight</em>:&nbsp;This operation updates the <em>size</em> of the image.</li>
</ul>

<p>After performing all the operations, the locked stub code prints the url and size of each image.</p>

<div class="ps-content-wrapper-v0">
<p>&nbsp;</p>
<!-- <StartOfInputFormat> DO NOT REMOVE THIS LINE-->

<details><summary class="section-title">Input Format For Custom Testing</summary>

<div class="collapsable-details">
<p>The first line contains an integer n, denoting the total number of images to be created initially.</p>

<p>Each of the next n lines contains 3 values - string url, number width, and number height for construction of n Image objects.</p>

<p>The next line contains the value of <em>numberOfOperations,</em> the total number of operations to be performed.</p>

<p>Each of the next <em>numberOfOperations</em> lines contains one of the three operations listed above.</p>
</div>
</details>
<!-- </StartOfInputFormat> DO NOT REMOVE THIS LINE-->

<details open="open"><summary class="section-title">Sample Case 0</summary>

<div class="collapsable-details">
<p class="section-title">Sample Input For Custom Testing</p>

<pre>STDIN&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;     Function
-----&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;     --------
2&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;→&nbsp;&nbsp;&nbsp;&nbsp;2 images to be created initially&nbsp;&nbsp;&nbsp;
hackerrank.com/image1 100 100&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;→&nbsp;&nbsp;&nbsp;&nbsp;url = 'hackerrank.com/image1', width = 100, height = 100
hackerrank.com/image2 200 200&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;→&nbsp;&nbsp;&nbsp;&nbsp;url = 'hackerrank.com/image2', width = 200, height = 200
3&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;→&nbsp;&nbsp;&nbsp;&nbsp;numberOfOperations = 3
Clone 1&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;→&nbsp;&nbsp;&nbsp;&nbsp;clones 1st image object
UpdateUrl 1 hackerrank.com/image3&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;→&nbsp;&nbsp;&nbsp;&nbsp;updates 1st image object's url to 'hackerrank.com/image3'
UpdateSize 2 300 400&nbsp;&nbsp;  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;→&nbsp;&nbsp;&nbsp;&nbsp;updates 2nd images object's width to 300 and height to 400
</pre>

<p class="section-title">Sample Output</p>

<pre>hackerrank.com/image3 100 100
hackerrank.com/image2 300 400
hackerrank.com/image1 100 100
</pre>

<p class="section-title">Explanation</p>

<p>The first line of input contains integer 2, which denotes 2 images that need to be created initially. 2 images are created with the inputs from the 2<sup>nd</sup> and 3<sup>rd</sup> lines. The next contains number 3, the number of operations to be performed. The next operation clones the images with id 1 (i.e. the first image object). The next line operation updates the url of the image with id 1 to 'hackerrank.com/image3'. The next operation updates the width and height of the image with id 2 to 300 and 400 respectively.</p>
</div>
</details>
</div>
<style type="text/css">.ps-content-wrapper-v0 div { margin: 0 auto; overflow: auto; } .ps-content-wrapper-v0 div.preheader { display: none; } .ps-content-wrapper-v0 p { white-space: pre-wrap; padding-left: 4px; padding-right: 4px; padding-top: 0px; padding-bottom: 2px; } .ps-content-wrapper-v0 p.section-title { font-weight: bold; padding-bottom: 0px; } .ps-content-wrapper-v0 ol.plain-list, .ps-content-wrapper-v0 ul.plain-list { list-style-type: none; padding: 4px; } .ps-content-wrapper-v0 li { white-space: normal; margin-top: 4px; margin-bottom: 4px; } .ps-content-wrapper-v0 code { color: black; } .ps-content-wrapper-v0 pre { background-color: #f4faff; border: 0; border-radius: 2px; margin: 8px; padding: 10px; } .ps-content-wrapper-v0 pre.scrollable-full-json { overflow-x: scroll; white-space: pre; } .ps-content-wrapper-v0 pre.scrollable-json { height: 300px; overflow-y: scroll; display: inline-grid; white-space: pre-wrap; padding-left: 8px; padding-right: 8px; padding-top: 4px; padding-bottom: 4px; } .ps-content-wrapper-v0 div.equation-parent { width: 400px; text-align: center; border: 1px solid #000; padding: 8px; } .ps-content-wrapper-v0 div.equation-parent.equation { width: 100%; display: inline-block; } .ps-content-wrapper-v0 figure { background-color: transparent; display: table; margin-top: 8px; margin-bottom: 8px; text-align: center; margin-left: auto; margin-right: auto; } .ps-content-wrapper-v0 figcaption { text-align: center; display: table-caption; caption-side: bottom; margin-top: 4px; margin-bottom: 4px; } .ps-content-wrapper-v0 img { width: auto; max-width: 100%; height: auto; } .ps-content-wrapper-v0 details { background-color: transparent; padding-left: 4px; padding-right: 4px; padding-top: 0px; padding-bottom: 2px; } .ps-content-wrapper-v0 details details { padding-left: 8px; padding-right: 8px; } .ps-content-wrapper-v0 details summary { background-color: #39424e; color: white; font-weight: bold; margin-top: 4px; margin-bottom: 4px; padding: 8px; } .ps-content-wrapper-v0 details details summary code { color: black; font-weight: bold; padding-left: 2px; padding-right: 2px; padding-top: 4px; padding-right: 4px; margin-left: 4px; } .ps-content-wrapper-v0 details div.collapsable-details { margin: 0 auto; padding-left: 4px; padding-right: 4px; padding-top: 0px; padding-bottom: 2px; overflow: auto; } .ps-content-wrapper-v0 details div.collapsable-details pre { margin-left: 4px; margin-right: 4px; margin-top: 4px; margin-bottom: 4px; } .ps-content-wrapper-v0 table.normal { border: 1px solid black; border-collapse: collapse; border-color: darkgray; margin: 0 auto; margin-top: 8px; margin-bottom: 8px; padding: 8px; width: 96%; table-layout: fixed; } .ps-content-wrapper-v0 table.normal tbody { display: block; overflow-x: auto; overflow-y: hidden; } .ps-content-wrapper-v0 table.normal tbody tr:first-child th { font-weight: bold; white-space: normal; } .ps-content-wrapper-v0 table.normal tbody tr th, .ps-content-wrapper-v0 table.normal tbody tr td { font-weight: normal; white-space: nowrap; text-align: center; vertical-align: middle; border: 1px solid black; border-color: darkgray; padding: 8px; } .ps-content-wrapper-v0 table.database-table { border-collapse: collapse; border-color: darkgray; border: 1px solid black; width: auto; margin-left: 4px; margin-top: 8px; margin-bottom: 8px; padding: 8px; } .ps-content-wrapper-v0 table.database-table tbody { overflow-x: auto; overflow-y: hidden; border: none; } .ps-content-wrapper-v0 table.database-table tbody tr th, .ps-content-wrapper-v0 table.database-table tbody tr td { font-weight: normal; white-space: nowrap; text-align: center; vertical-align: middle; border: 1px solid black; border-color: darkgray; padding: 8px; } .ps-content-wrapper-v0 table.database-table tbody tr th { font-weight: bold; border: 1px solid black; } .ps-content-wrapper-v0 table.database-table tbody tr:nth-child(2) td { border: 1px solid black; } .ps-content-wrapper-v0 table.database-table tbody tr:nth-child(n+2) td:first-child { border-left-color: black; } .ps-content-wrapper-v0 table.database-table tbody tr:nth-child(n+2) td:last-child { border-right-color: black; } .ps-content-wrapper-v0 table.database-table tbody tr:last-child td { border-bottom-color: black; } .ps-content-wrapper-v0 table.database-table tbody tr td.description { text-align: left; white-space: pre-wrap; } .ps-content-wrapper-v0 table.normal tbody tr th.description { width: 60%; } .ps-content-wrapper-v0 table.function-params tbody tr:first-child td.headers { border-bottom-width: 2px; } .ps-content-wrapper-v0 table.function-params tbody tr:last-child td { border-top-width: 2px; border-top-color: darkgray; } .ps-content-wrapper-v0 table.function-params tbody tr td.headers { width: 25%; font-weight: bold; text-align: center; border: 1px solid black; border-right-width: 2px; border-color: darkgray; } .ps-content-wrapper-v0 table.function-params tbody tr td.params-table-cell { width: 100%; height: 100%; padding: 0px; } .ps-content-wrapper-v0 table.function-params tbody tr td.params-table-cell table.params-table { width: 100%; height: 100%; padding: 0px; margin: 0px; border: 0; } .ps-content-wrapper-v0 table.function-params tbody tr td.params-table-cell table.params-table tbody tr td.code { white-space: normal; } .ps-content-wrapper-v0 table.function-params tbody tr td.params-table-cell table.params-table tbody tr th { border-top: 0; } .ps-content-wrapper-v0 table.function-params tbody tr td.params-table-cell table.params-table tbody tr th:first-child { border-left: 0; } .ps-content-wrapper-v0 table.function-params tbody tr td.params-table-cell table.params-table tbody tr th:last-child { border-right: 0; } .ps-content-wrapper-v0 table.function-params tbody tr td.params-table-cell table.params-table tbody tr:last-child td { border-bottom: 0; border-top-width: 1px; } .ps-content-wrapper-v0 table.function-params tbody tr td.params-table-cell table.params-table tbody tr td:first-child { border-left: 0; } .ps-content-wrapper-v0 table.function-params tbody tr td.params-table-cell table.params-table tbody tr td:last-child { border-right: 0; } .ps-content-wrapper-v0 table.sudoku { border-collapse: collapse; border-color: darkgray; margin: 0 auto; margin-top: 8px; margin-bottom: 8px; padding: 8px; } .ps-content-wrapper-v0 table.sudoku colgroup, tbody { border: 3px solid black; } .ps-content-wrapper-v0 table.sudoku td { border: 1px solid black; height: 25px; width: 25px; text-align: center; padding: 0; } .ps-content-wrapper-v0 .left { text-align: left; } .ps-content-wrapper-v0 .right { text-align: right; } .ps-content-wrapper-v0 .code { font-family: monospace; white-space: nowrap; } .ps-content-wrapper-v0 .json-object-array ol, .ps-content-wrapper-v0 .json-object-array ol ul { margin-top: 0px; padding-left: 14px; } .json-object-array li { float: left; margin-right: 30px; margin-left: 10px; } .json-object-array pre { padding: 4px; margin-left: 0px; }
</style>
</div>