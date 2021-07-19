## idea报Command line is too long

### 解决方案

需要在该项目文件夹下.idea/workspace.xml中查找name属性为```PropertiesComponent```的component标签，然后添加如下property标签即可。

```xml
<component name="PropertiesComponent">
  ...
  <property name="dynamic.classpath" value="true" />
</component>
```

