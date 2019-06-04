### charles 破解
1. 具体方式使用jar反编译工具，在charles.jar`com.xk72.charles`目录下寻找代码中包含
``` java
 "Thanks for looking at the source. Please register Charles if you use it."
```
2. 参考下面,保留并处理 `public static * * ()`的方法，然后编译并替换
``` sh
charles=/Applications/Charles.app/Contents/Java/charles.jar
dir=charleshack

mkdir $dir
cd $dir
cat >> oFTR.java <<EOF
package com.xk72.charles;
public final class oFTR {
	public static boolean Yuaz() { return true; }
	public static String lktV() { return "Administrator"; }
	public static String Yuaz(String name, String key) { return null; }
}
EOF
javac -encoding UTF-8 oFTR.java -d .&& jar -uvf $charles com/xk72/charles/oFTR.class
cd .. && rm -rf $dir
```
### 下载地址
[charles 官方下载地址](https://www.charlesproxy.com/download/)