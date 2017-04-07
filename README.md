# String-StringBuilder-
String和StringBuilder的效率
用StringBuilder循环的拼接10000次字符串需要的时间为 0到1毫秒


        long tt = long.Parse(DateTime.Now.ToString("yyyyMMddHHmmssfff"));

        StringBuilder start = new StringBuilder();
        for(int j=0;j<10000;j++)
        {
            start.Append("测试测试测试测试测试测试测试测试测试测试测试测试");
        }

        long mm = long.Parse(DateTime.Now.ToString("yyyyMMddHHmmssfff"));

        Response.Write(Convert.ToString( mm-tt));

用string循环的拼接100000次字符串需要的时间为 5500到6000毫秒！

代码如下：

long tt = long.Parse(DateTime.Now.ToString("yyyyMMddHHmmssfff"));

        string start =string.Empty;
        
        for(int j=0;j<10000;j++)
        {
            start += "测试测试测试测试测试测试测试测试测试测试测试测试";
        }

        long mm = long.Parse(DateTime.Now.ToString("yyyyMMddHHmmssfff"));

        Response.Write(Convert.ToString( mm-tt));

我原本用的是100000 次拼接做的测试，StringBuilder仅用了30毫秒，但是用string拼接就执行几分钟没有执行完，所以我就改用10000次来做试验了！

简单的可以概括为，string拼接的次数越多，速度则越慢，而StringBuilder则几乎没有变化
