# B站使用文档

## 主题样式

[相关CSDN](https://blog.csdn.net/weixin_42272768/article/details/100978209)

```
import tkinter as tk
from tkinter import ttk
root=tk.Tk()
s=ttk.Style()
print(s.theme_names())
root.mainloop()

```

# 评论数

https://api.bilibili.com/x/v2/reply/main?**next**=1&**type**=1&**oid**=33374149&**mode**=3&**plat**=1&_=1623562995923

1. mode: 1评论  | 2最新评论 | 3热门评论
2. next 第几页
3. oid：访问数据文件夹中excel文件的`id`列
4.

```

https://api.bilibili.com/x/v2/reply?jsonp=jsonp&pn=2&type=1&oid=39807126&sort=2&_=1563294527125，

可以得到 json 格式的评论。其中参数 pn 是评论的页数 ；

 oid 就是视频网址后面的 av那一串数字；
sort一看就清楚是排序方式，
0是按时间排序，
2是按热度；最后面的参数似乎没有什么影响。
```

[grid布局](https://www.cnblogs.com/ruo-li-suo-yi/p/7425307.html)


加粗奇数列

```python
    def InsertValueToTree(self,col_df):
        "添加数据到表格中，并设置列的宽度"
        for col_index,col_name in enumerate(col_df.columns.tolist(),start=1):
            self.tv.heading(col_index,text=col_name,\
                command=lambda _col=col_index: self.treeview_sort_column(self.tv,_col, False))

        #第一列（标题）宽度较大，其他列宽度较小，点击数字列具有排序功能
        for col_index,col_name in enumerate(col_df.columns.tolist(),start=1):
            if col_index ==1:
                self.tv.column(col_index, width=250, anchor='w') 
            else:
                self.tv.column(col_index, width=80, anchor='center') 
            self.tv.heading(col_index,text=col_name,\
                command=lambda _col=col_index: self.treeview_sort_column(self.tv,_col, False))
      
        for col_index,col_name in enumerate(col_df.values.tolist(),start=1):
            if col_index &1:
                self.tv.insert(parent='',index=col_index, iid=col_index,  values=col_name, tags = ('oddrow',))
            else:
                self.tv.insert(parent='',index=col_index, iid=col_index,  values=col_name, tags = ('evenrow',))
        self.BoldOddLine()

    def BoldOddLine(self):  
        "奇数行字体加粗"
        items = self.tv.get_children()  # 获取所有的单元格
        for index,item in enumerate(items,start=1):
            if index&1:
                self.tv.item(item,tags='oddrow')  # 对每一个单元格命名
                self.tv.tag_configure('oddrow',font='SimHei 14 bold', background="#ff008c")  # 设定treeview里字体格式font=ft
            else:
                self.tv.item(item,tags='evenrow')  # 对每一个单元格命名
                self.tv.tag_configure('evenrow',font='SimHei 14', background='pink')  # 设定treeview里字体格式font=ft
        self.tv.update()  # 更新tree
```
