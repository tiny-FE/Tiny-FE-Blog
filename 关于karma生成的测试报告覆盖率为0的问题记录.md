#### 问题表现： 组件写了测试用例并且可以跑通但在生成的测试报告中显示该组件的覆盖率为0

如下图：![0%](http://blog-images.fiveseven.top/karma-%E6%B5%8B%E8%AF%95%E6%8A%A5%E5%91%8A0%25.png)

#### 猜测：方法写在template里，组件的<script>标签内没有能检测到的js方法。

#### 验证：将方法写到<script>内的methods里，这时候能正确的显示出覆盖率。

![100%](http://blog-images.fiveseven.top/karma-%E6%B5%8B%E8%AF%95%E6%8A%A5%E5%91%8A100%25.png)


