# Proxy 和 GSE 后台之间的网络策略

源地址|目标地址|协议|端口|用途
--|--|--|--|--
proxy(gse_agent)|gse_task|TCP|48533|任务服务端口
proxy(gse_transit)|gse_data|TCP|58625|数据上报端口
proxy(gse_btsvr)|gse_btsvr|TCP|58930|bt 传输
proxy(gse_btsvr)|gse_btsvr|TCP,UDP|10020|bt 传输
proxy(gse_btsvr)|gse_btsvr|UDP|10030|bt 传输
gse_btsvr|proxy(gse_btsvr)|TCP|58930|bt 传输
gse_btsvr|proxy(gse_btsvr)|TCP,UDP|10020|bt 传输
gse_btsvr|proxy(gse_btsvr)|UDP|10030|bt 传输
proxy(gse_btsvr)|proxy(gse_btsvr)|TCP|58930|bt 传输（同一子网）
proxy(gse_btsvr)|proxy(gse_btsvr)|TCP,UDP|10020|bt 传输（同一子网）
proxy(gse_btsvr)|proxy(gse_btsvr)|UDP|10030|bt 传输（同一子网）
proxy(gse_opts)|gse_ops|TCP|58725|ping 告警数据上报端口
proxy(gse_agent)|||监听随机端口|bt 传输，可不开通
proxy(gse_btsvr)|||监听随机端口|bt 传输，可不开通
