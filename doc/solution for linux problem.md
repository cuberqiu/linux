# The summary for solution for linux problem

## Ubuntu17.04安装Atom编辑器
添加atom仓库：  
sudo add-apt-repository ppa:webupd8team/Atom  
update:  
sudo apt-get update  
安裝Atom  
sudo apt-get install atom  

> 在用户模式下使用爱他Atom时，建议将用户添加到root组中

## Atom必要的插件
- linter
- git-plus
- autocomplete-python
- highlight-selected
- highlight-line
- markdown-preview
- script
- ask-stack
- Hydrogens(ipython,pip,jupyter)
  > apt-get install python-pip  
  > apt-get install ipython  
  > pip install jupyter  
  > pip install ipykernel
  >{  
  "kernelspecs": {  
    "python2": {  
      "spec": {  
        "display_name": "Python 2",  
        "language": "python",  
        "argv": ["python2.7", "-m", "ipykernel", "-f", "{connection_file}"],  
        "env": {}  
      }
    }  
  }  
}    
- Platformio Ide Terminal  


> Atom安装插件失败解决方案：  
> apt-get install npm  
> npm config set registry https://registry.npm.taobao.org  
>

## 添加用戶到root組
將newuser添加到root組中：  
usermod -G root newuser  
修改newuser用戶名：  
usermod -l newuser newname  

## Ubuntu上查看自己hostname
uname -n

## Github SSH相关问题
### Checking for existing SSH keys
ls -al ~/.ssh  
### Generating a new SSH key and adding it to the ssd-agent
#### Generating a new SSH key
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
#### Adding your SSH key to the ssh-agent
1. Start the ssh-agent in the background  
eval "$(ssh-agent -s)"
2. Add your SSH private key to the ssh-agent  
ssh-add ~/.ssh/id_rsa
3. Add the SSH key to your GitHub account

## 解决Ubuntu安装chrome没有图标的问题
1. 安装：  
sudo dokg -i google-chrome-stable_current_amd64.deb
2. 解决图标问题
sudo apt-get -f install


## 英文版linux安装中文输入法
1. 首先安装fcitx
```
sudo add-apt-repository ppa:wengxt/fcitx-nightly
sudo apt-get update 
sudo apt-get install  fcitx
```
2. 将fcitx设置为首选输入法
System Settings -> Language Support -> Keyboard input method system 选择 fcitx
3. 安装中文输入法
```
sudo apt-get install fcitx-sunpinyin  #下边的都是输入法，可安装任意一个

fcitx-pinyin
fcitx-sunpinyin
fcitx-libpinyin 
fcitx-googlepinyin
fcitx-table-wbpy #五笔加拼音的输入法
fcitx-table-wubi #五笔输入法
```
4. 注销或者重启一下系统就可以使用了。Ctrl + Space 为切换输入法的快捷键.  
如果输入法选项里没有出现输入法，就需要到系统设置里设置一下: System Settings -> Text Entry -> add fcitx