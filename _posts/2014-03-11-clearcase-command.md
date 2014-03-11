---
layout: post
title: ClearCase 常用命令
description: ClearCase做配置管理的工具。是RATIONAL公司开发的配置管理工具(现已被IBM收购)，类似于VSS，CVS的作用，但是功能比VSS，CVS强大的多，而且可以与WINDOWS资源管理器集成使用，并且还可以与很多开发工具集成在一起使用。
keywords: clearcase, command, 常用命令
category: IBM
---

ClearCase做配置管理的工具。是RATIONAL公司开发的配置管理工具(现已被IBM收购)，类似于VSS，CVS的作用，但是功能比VSS，CVS强大的多，而且可以与WINDOWS资源管理器集成使用，并且还可以与很多开发工具集成在一起使用。

###常用操作
<table width="100%">
	<tbody >
		<tr>
			<th width="20%">命令</th>
			<th width="40%">示例</th>
			<th width="40%">解释</th>
		</tr>
		<tr>
			<td>co -nc filename/dir</td>
			<td><code class="v-code">co -nc hello</code></td>
	    <td>check out file or folder</td>
		</tr>
		<tr>
			<td>ci -nc filename/dir</td>
			<td><code class="v-code">ci -nc hello</code></td>
	    <td>check in file or folder</td>
		</tr>
		<tr>
			<td>unco filename/dir</td>
			<td><code class="v-code">unco hello</code></td>
	    <td>undo checkout file or folder</td>
		</tr>
		<tr>
		  <td>lsco -r dir</td>
			<td><code class="v-code">lsco -r hello</code></td>
	    <td>list all the file or folder checkouted</td>
		</tr>
	</tbody>
</table>

###视图(View)
<table width="100%">
	<tbody >
		<tr>
			<th width="20%">命令</th>
			<th width="40%">示例</th>
			<th width="40%">解释</th>
		</tr>
		<tr>
			<td>Create a new stream that is using certain baseline</td>
			<td><code class="v-code">mkstream -in fod_intransit_01.00_integration@/vobs/nbst_pvob07 -bas fod_intransit_01.00_3_29_2012@/vobs/nbst_pvob07 -readonly fod_intransit_checkout_testing@/vobs/nbst_pvob07</code></td>
	    <td>Replace the integration stream name (first parameter after –in) with your integration stream name
Replace the baseline stream name (first parameter after –base) with your baseline name
Replace the new created stream name (first parameter after –readonly) with your new stream name (you can define this name using your own discretion)
    </td>
		</tr>
		<tr>
			<td>Create a view of the designated or new created stream</td>
			<td><code class="v-code">mkview -tag e483649_fod_intransit_checkout_testing.00_int -tcomment "e483649 transparent textmode INT stream view for fod_intransit_checkout_testing" -tmode transparent -stream fod_intransit_checkout_testing@/vobs/nbst_pvob07 -stgloc -auto</code></td>
		  <td>Replace the view tag,  comments and stream information with correct information in the above command and execute it.  Please note the stream name (first parameter after –stream) should be your new created stream or the stream name app owner sent to you for downloading required baseline)</td>
		</tr>
		<tr>
			<td>Set view to the created view</td>
			<td><code class="v-code">setview e483649_fod_intransit_checkout_testing.00_int</code></td>
			<td>Using your own view created in above step</td>
		</tr>
		<tr>
		  <td>Remove the created view</td>
			<td><code class="v-code">rmview -tag e483649_fod_intransit_checkout_testing.00_int</code></td>
			<td>Remove the view</td>
		</tr>
	</tbody>
</table>


