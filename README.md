# HTMLTestRunner
优化了HTMLTestRunner的报告页面


使用修改了原有的部分样式，添加了chart图表

使用方法跟原先的HTMLTestRunner一样，不过需要安装bottle模块


#-*- coding:utf-8 -*-
#!/usr/bin/env python
import time
import unittest
from utils.HTMLTestRunner import HTMLTestRunner

d='../'
discover = unittest.defaultTestLoader.discover(d, pattern='tes.py')
print(discover)
if __name__ == '__main__':
    now = time.strftime("%Y-%m-%d %H_%M_%S")
    # filename='../logs/' + now + 'report.html'
    filename='e:test.html'
    fp = open(filename, 'w',encoding='utf-8')
    runner = HTMLTestRunner(stream=fp,
                            title='TestReport',
                            description='test result')
    runner.run(discover)

