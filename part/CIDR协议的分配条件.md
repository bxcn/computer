为了确保CIDR（Classless Inter-Doman Routing, CIDR 无类别域间路由）正确工作，连续分配一组B类或C类地址时，这组地址必须满足如下条件：
- 这组地址必须是连续的
- 这组地址的数量必须是2的指数，设为2<sup>n</sup>个
- 这组地址的起始地址必须保证能被2<sup>n</sup>整除

