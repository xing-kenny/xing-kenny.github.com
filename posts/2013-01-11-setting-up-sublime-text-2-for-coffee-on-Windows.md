<h2 align="center"><font size="16" color="blue">Setting up sublime text 2 for coffee on Windows</font></h2>
 
## 1.  npm install -g coffee-script
## 2.  Syntax coloring
download CoffeeScript.tmLanguage from 'https://github.com/jashkenas/coffee-script-tmbundle/tree/master/Syntaxes',
save to "Sublime Text 2\Data\Packages\CoffeeScript".
## 3.  create new Build System
Tools -> Build System -> New Build System...    	
with

    {
	"cmd": ["E:\\run\\nodejs\\coffee.cmd", "$file"],
	"file_regex": "^(...*?):([0-9]*):?([0-9]*)",
	"selector": "source.coffee"
	}

save as "Sublime Text 2\Data\Packages\CoffeeScript\CoffeeScript.sublime-build"

### note: CoffeeScript.sublime-build && CoffeeScript.tmLanguage need save to same folder. 

## 4.  test
* select Build System , Tools -> Build System -> CoffeeScript
* create a coffee file
* run CTRL+B

now OK...
## 5. ref

[http://coffeescript.org]

[CoffeeScript的Sublime Text 2开发环境配置]	

[http://coffeescript.org]: http://coffeescript.org/#language
[CoffeeScript的Sublime Text 2开发环境配置]: http://www.cnblogs.com/2gua/archive/2012/07/05/2577603.html
