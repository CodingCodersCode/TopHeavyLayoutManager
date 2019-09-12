# TopHeavyLayoutManager
Customize the LayoutManager of RecyclerView(自定义LayoutManager)
# Effect display
<img width="320" height="564" src="https://github.com/ljm17/TopHeavyLayoutManager/raw/master/images/display.gif"/><br/>
# Usage
### Dependency：
Step 1. Add the JitPack repository to your build file

```
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
```
<br/>

Step 2. Add the dependency

```
dependencies {
	        implementation 'com.github.ljm17:TopHeavyLayoutManager:1.0.0'
	}
```

### Explain：
构造方法：<br/>
```
//TopHeavyLayoutManager
TopHeavyLayoutManager();
TopHeavyLayoutManager(int space);
TopHeavyLayoutManager(float childScale, float coverScale);
TopHeavyLayoutManager(int space, float childScale, float coverScale);

//TopSnapHelper
TopSnapHelper(int fillingLimit);
```

参数|介绍
-|-
space|相邻child view之间的距离|
childScale|尾部child view的缩放值|
coverScale|头部被覆盖的child view的缩放值|
fillingLimit|手指离开后filling的页数限制|

<br/>
如果想要实现无限循环，只需在RecyclerView.Adapter的getItemCount中返回Integer.MAX_VALUE，设置无限循环后，默认首个展示的item position为Integer.MAX_VALUE/2，若需调整请调用RecyclerView.scrollToPosition(position)方法

### Example：
```
mRecyclerView.setLayoutManager(new TopHeavyLayoutManager());
mRecyclerView.setAdapter(new xxxAdapter());
TopSnapHelper helper = new TopSnapHelper(2);
helper.attachToRecyclerView(mRecyclerView);
```

# License
Licensed under the Apache License, Version 2.0 (the "License");<br/>
   you may not use this file except in compliance with the License.<br/>
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.<br/>
   See the License for the specific language governing permissions and
   limitations under the License.