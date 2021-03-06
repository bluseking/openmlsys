## 总结

- 不同的模型部署场景下，通常对于模型大小、运行时内存占用、推理时延和推理功耗等指标有限制。

- 针对模型大小指标，通常在离线阶段通过模型压缩技术来优化，比如量化技术、剪枝技术、知识蒸馏技术等，除此之外，一部分模型优化技术，比如融合技术 :numref:`ch08-sec-fusion`等，也有助于模型轻量化，不过其效果比较微弱。

- 针对运行时内存指标，主要有三方面的优化：优化模型大小、优化部署框架包大小以及优化运行时临时内存。模型大小的优化手段在上一点中已经说明；部署框架包大小主要通过精简框架代码、框架代码模块化等方式来优化。运行时临时内存主要通过内存池实现内存之间的复用来优化，这部分可以参见 :numref:`ch05-sec-memory_pool`。

- 针对模型的推理时延指标，主要有两方面的优化，一方面是离线时通过模型优化技术 :numref:`ch08-sec-fusion`和模型压缩技术 :numref:`ch08-sec-model_compression`尽可能降低模型推理所需的计算量；另一方面是通过加大推理的并行力度 :numref:`ch08-sec-parallel_inference`和优化算子实现 :numref:`ch08-sec-kernel_optimization`来充分挖掘硬件的计算潜力。值得注意的是，除了考虑计算量和算力，推理时的访存开销也是一个重要的影响因素，这一点在 :numref:`ch08-sec-fusion`小节和 :numref:`ch08-sec-kernel_optimization`小节中进行了相关优化。
  
- 针对模型的推理功耗，主要的优化思路是降低模型的计算量，这与针对模型推理时延的优化手段有重合之处，可以参考离线的模型优化技术 :numref:`ch08-sec-fusion`和模型压缩技术 :numref:`ch08-sec-model_compression`。
  
- 本章除了介绍优化模型部署的各方面指标的优化技术以外，还介绍了安全部署相关的技术，如模型混淆、模型加密等。部署安全一方面可以保护企业的重要资产，另一方面可以防止黑客通过篡改模型从而入侵攻击部署环境。
