在线学习：一个数据点训练完了直接更新权重（而不是一个batch），
看到了没？直接更新权重，这里有危害处！（我们无法得知这一次的更新权重是正确的还是错误的，
如果恰恰是错误的一次更新，那么我们的模型会有可能渐渐地走向错误方向，残差出现）


离线学习：batch learning一个batch训练完才更新权重，这样的话要求所有的数据必须在每一个
训练操作中（batch中）都是可用的，个人理解，这样不会因为偶然的错误把网络带向极端。
