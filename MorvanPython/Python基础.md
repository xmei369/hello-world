
# 多进程


```python
import multiprocessing as mp

def job(a,d):
    print('aaaa')

if __name__=='__main__':
    p1 = mp.Process(target=job, args=(1,2))
    p1.start()
    p1.join()

# 保存后运行脚本即可。

# threading与processing很相似
import threading as td

t1 = td.Tread(target=job, args=(1,2))
p1 = mp.Process(target=job, args=(1,2))
t1.start()
p1.start()
t1.join()
p1.join()



```

# 关于jupyter notebook
  
[入门](#https://baijiahao.baidu.com/s?id=1601883438842526311&wfr=spider&for=pc)  
[快速入门3](#https://blog.csdn.net/taotiezhengfeng/article/details/72842817)  
  
## 快捷键
用Esc和Enter在命令模式和编辑模式之间跳跃。  
a 会在活跃单元之上插入一个新的单元  
b 会在活跃单元之下插入一个新单元  
dd 可以删除一个单元  
z 撤销被删除的单元  
y 会将当前活跃的单元变成一个代码单元  
m 把代码单元变成标记单元  
Shift +上或下箭头 可选择多个单元  
Shift + M 在多选模式时，可合并你的选择  
f 会弹出「查找和替换」菜单  
  
处于编辑模式时：  
Ctrl + Home 到达单元起始位置  
Ctrl + s 保存进度  
Ctrl + Enter 会运行你的整个单元块  
Alt + Enter 不止会运行你的单元块，还会在下面添加一个新单元  
Ctrl + Shift + F 打开命令面板  
Crtl + / 为一行或者多行添加/取消注释  
  
要查看键盘快捷键完整列表，可在命令模式按「H」或进入「Help > Keyboard Shortcuts」。  


```python
%lsmagic # “神奇”magic的命令
```




    Available line magics:
    %alias  %alias_magic  %autoawait  %autocall  %automagic  %autosave  %bookmark  %cd  %clear  %cls  %colors  %config  %connect_info  %copy  %ddir  %debug  %dhist  %dirs  %doctest_mode  %echo  %ed  %edit  %env  %gui  %hist  %history  %killbgscripts  %ldir  %less  %load  %load_ext  %loadpy  %logoff  %logon  %logstart  %logstate  %logstop  %ls  %lsmagic  %macro  %magic  %matplotlib  %mkdir  %more  %notebook  %page  %pastebin  %pdb  %pdef  %pdoc  %pfile  %pinfo  %pinfo2  %popd  %pprint  %precision  %prun  %psearch  %psource  %pushd  %pwd  %pycat  %pylab  %qtconsole  %quickref  %recall  %rehashx  %reload_ext  %ren  %rep  %rerun  %reset  %reset_selective  %rmdir  %run  %save  %sc  %set_env  %store  %sx  %system  %tb  %time  %timeit  %unalias  %unload_ext  %who  %who_ls  %whos  %xdel  %xmode
    
    Available cell magics:
    %%!  %%HTML  %%SVG  %%bash  %%capture  %%cmd  %%debug  %%file  %%html  %%javascript  %%js  %%latex  %%markdown  %%perl  %%prun  %%pypy  %%python  %%python2  %%python3  %%ruby  %%script  %%sh  %%svg  %%sx  %%system  %%time  %%timeit  %%writefile
    
    Automagic is ON, % prefix IS NOT needed for line magics.




```python
%time a = range(10)
```

    Wall time: 0 ns
    


```python
%%timeit a = range(10)min(a)
```

    UsageError: %%timeit is a cell magic, but the cell body is empty. Did you mean the line magic %timeit (single %)?
    


```python
! echo 'hello' # 调用系统命令，前面加感叹号
! python --version
```

    'hello' # 调用系统命令，前面加感叹号
    Python 3.7.0
    
