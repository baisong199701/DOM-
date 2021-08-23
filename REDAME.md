# DOM编程
## 网页其实是一颗树
### JS如何操作这棵树
* 浏览器往window上加一个document即可
### JS用document操作网页
* 这就是Document Object Model 文档对象模型
### 获取元素，也叫标签
* 有很多API
1. window.index或者直接index
2. document.getElementByid('index')
3. document.getElementsByTagName('div')[0]
4. document.getElementsByClassName('red')[0]
5. document.querySelector('#idxxx')
6. document.querySelectorAll('.red')[0]
* 用哪一个
1. 工作中用querySelector和querySelectorAll
2. 做demo直接用idxxx
### 获取特定元素
* 获取html元素：document.documentElement
* 获取head元素：docunment.head
* 获取body元素：document.body
* 获取窗口：window
* 获取所有元素：document.all //这个是第6个falsy值
### 获取的到的元素是对象
## 节点Node包含一下等
1. 表示元素Element,也叫标签Tag
3. 表示文本Text
## 节点的增删改查
### 增
* 创建一个标签节点
````
    let div1 = document.creatElement('div')
    document.creatElement('style')
    document.creatElement('script')
    document.creatElement('li')
````
* 创建一个文本节点
````
    text1 = document.creatTextNode('你好')
````
* 标签里面插入文字
````
    div1.appendChild(text1)
    div1.innerText='你好'或者div1.textContent='你好'
````
### 删
* 两种方法
1. 旧方法：parentNode.childChild(childNode)
2. 新方法：childNode.remove()
### 改属性
* 改class:
````
    div.className='red blue' (全覆盖)
····
* 改class:
````
    div.classList.add('red')
````
* 改style:
````
    div.style = 'width:100px;color:blue;'
````
* 改style的一部分
````
    div.style.width='200px'
````
* 读标准属性
1. div.classList/a.href
2. div.getAttribute('class')/a.getAttribute('href')  //两种方法都可以，但值可能稍微有些不同

### 改时间处理函数
* div.onclick默认为null  
1. 默认点击div不会有任何事情发生，但是如果你把div.onclick改成一个函数，那么点击div的时候，浏览器就会调用这个函数，并且是这样的调用fn.call(div,event)div会当做this,event则包含了点击事件的信息
* div.addElentListener:是div.onclick的升级版
### 改内容
* 改文本内容
````
    div.innerText='xxx'
    div.textContent='xxx'
    两者几乎没有区别
````
* 改HTML内容
````
    div.innerHTML='<strong>重要内容</strong>
````
* 改标签
````
    div.innerHTML='' //先清空
    div.appendChild(div2) //再加内容
````
* 改爸爸
````
    newParent.appendChild(div)
````
### 查
* 查爸爸
````
    node.parentNode 或者 node.parentElement
````
* 查爷爷
````
    node.parentNode.parentNode
````
* 查子代
````
    node.childNodes 或者node.children
````
* 查兄弟姐妹
````
    node.parentNode.childNodes  还要排除自己
    node.parentNode.children  还要排除自己
````
* 查看老大
````
    node.firstChild
````
* 查看老幺
````
    node.lastChild
````
* 查看上一个哥哥/姐姐
````
    node.previousSibling
````
* 查看下一个弟弟/妹妹
````
    node.nextSibling
````













































































    
    
    
    
    
    
    
    
    
    
    
   
    
    
    
    
    
    
    
    
    
