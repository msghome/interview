# HTML代码规范
1. 不要把表格用于页面布局。
2. 列表项放\<ul>、\<ol>、\<dl>，不要使用一系列的\<div>或\<p>或\<span>\<i>。
3. html标签、html属性全部小写。
4. 嵌套。所有元素必须正确嵌套。
5. 闭合。双标签必须闭合，单标签（自关闭标签）不闭合。
6. 详尽注释。解释代码解决问题、解决思路、是否为新鲜方案等。
7. 模块注释。github建议不使用模块结束注释。
8. 待办注释。<!-- TODO:待办事项 -->
9. 文档类型使用html5标准文档类型<!DOCTYPE html>。
10. html元素上指定lang属性。<html lang="cn">。
11. 指定明确的字符编码，<meta charset="UTF-8">。
12. IE兼容模式，<meta http-equiv="X-UA-Compatible" content="IE=Edge">。
13. 可以使用IE条件注释的方式兼容IE，但是不要添加额外的样式表。<!--[if IE8]><html class="ie8" lang="zh-cn"><![endif]-->
14. 双引号属性值，不要使用单引号。
15. 省略type属性。使用style、link、script，不用指定type属性，因为 text/css 和 text/javascript 分别是他们的默认值。
16. 省略Boolean属性值。Boolean属性不用添加取值，disabled,checked,selected等。
17. 省略url类属性资源协议头。
18. 属性顺序。html属性应该按照特定的顺序出现以保证易读性。class->id,name->data-*->src,for,type,href->title,alt->aria-*,role。
19. 多媒体元素添加替代属性。图像增加alt属性，音视频增加替代文字。
20. 不手动设置tabindex属性，让浏览器自动设置。
21. 避免冗余标签。
22. 避免JS生成标签。
23. 段落文字应该用\<p>，避免使用\<br>。
24. \<input>使用for属性绑定<label>。
25. 使用<label>标签包裹radio或checkbox和他们的文字，不用再使用for属性。
26. 使用单选、复选替代下拉菜单。（radio or checkbox instead of select menu）
27. form button应制定type类型，使用type="submit"、type="reset"或type="button"。
28. 首要的表单按钮首先出现(在DOM中)，尤其是适用多个提交按钮的场合。视图中显示的顺序可以利用css修改。
29. 有效使用\<thead>、\<tfoot>、\<tbody>、\<th>（scope属性）。可以把\<tfoot>放\<tbody>前提高加载速度。
30. 空格尽量用样式，避免使用&nbsp;
31. 使用二个空格的 soft tabs。
32. 嵌套缩进。
33. 删除行尾空格。
34. 块元素、列表元素、表格元素都放在新行,inline元素视情况换行。
35. 努力保持每行长度小于80列，如果太长可换行。
	
		<img  
		  class="block_element"  
		  id="unicorn"  
		  src="http://cl.ly/image/1a1u013e002z"  
		  alt="unicorn, rainbows, poop and stuff"  
		  width="500" 
		  height="400" 
		>
    
    

    