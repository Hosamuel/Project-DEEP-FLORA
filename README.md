# DEEP-FLORA

Deep-Flora é um sistema simples e de fácil acesso projetado para reconhecer automaticamente uma ampla variedade de espécies de plantas a partir de imagens. A proposta é contribuir com áreas como botânica, agricultura e estudos ambientais, oferecendo uma ferramenta acessível para identificação precisa de espécies.

O projeto utiliza conjuntos de dados públicos, extenso e diversificado, combinando imagens de diferentes fontes. Por meio de técnicas de Deep Learning e Transfer Learning, o sistema foi treinado com uma arquitetura moderna de redes neurais convolucionais, visando alto desempenho mesmo diante da variabilidade visual entre as espécies.

## Desenvolvimento do Projeto
O projeto está em aberto, mas em fase de finalização. Os resultados obtidos até o momento indicam uma evolução significativa a cada nova atualização.

Duas redes neurais promissoras foram testadas, com desempenho satisfatório. O processo de análise comparativa e escolha do modelo final foi conduzido em um Jupyter Notebook principal — disponível em [main.ipynb](main.ipynb). Esse notebook inclui:

- Bibliotecas utilizadas para o desenvolvimento
- Análise quantitativa dos dados adquiridos
- Avaliação de desempenho dos modelos testados
- Definição da arquitetura final adotada para o projeto

# Dataset
O conjunto de dados é composto por milhares de imagens de plantas, organizadas em três subconjuntos:

Treinamento: Imagens usadas para treinar o modelo de classificação.
Validação: Imagens para ajuste de hiperparâmetros.
Teste: Imagens para avaliação final no desempenho do modelo.

## Modelo Utilizado
Para construir o modelo de classificação, foi utilizada a técnica de Transfer Learning com base em uma arquitetura pré-treinada, permitindo uma melhor performance mesmo com menos dados e menos tempo de treinamento. A arquitetura escolhida foi:

Arquitetura Base: ResNet50 e o modelo gerado foi: model.pth.
Pesos Pré-Treinados: weights.pth.
Os pesos do modelo foram ajustados para identificar espécies de plantas, adaptando as camadas finais para a classificação específica das classes do conjunto de dados.

## Referências
Baumbach, L., Schmidt, C., & Michalik, A. (2019). Big data and citizen science—An integration towards data-driven sustainable development. Sustainability, 11(4), 956. https://doi.org/10.3390/su11040956.

BFG – The Brazil Flora Group. (2018). Brazilian Flora 2020: Innovation and collaboration to meet Target 1 of the Global Strategy for Plant Conservation. Rodriguésia, 69(4), 1513–1527. https://doi.org/10.1590/2175-7860201869402.

Chen, Y., Huang, Y., Zhang, Z., Wang, Z., Liu, B., Liu, C., Huang, C., Dong, S., Pu, X., Wan, F., Qiao, X., & Qian, W. (2023). Plant image recognition with Deep Learning: A review. Computers and Electronics in Agriculture, 212, 108072. https://doi.org/10.1016/j.compag.2023.108072.

Goodfellow, I., Bengio, Y., & Courville, A. (2016). Deep Learning. MIT Press.

Gulzar, Y. (2023). Fruit image classification model based on MobileNetV2 with deep transfer learning technique. Sustainability, 15(3), 1906. https://doi.org/10.3390/su15031906.

Krizhevsky, A., Sutskever, I., & Hinton, G. E. (2012). ImageNet classification with deep convolutional neural networks. In Advances in Neural Information Processing Systems 25 (NIPS 2012) (pp. 1097–1105).

LeCun, Y., Bengio, Y., & Hinton, G. (2015). Deep Learning. Nature, 521(7553), 436–444. https://doi.org/10.1038/nature14539.
LeCun, Y., Kavukcuoglu, K., & Farabet, C. (2010). Convolutional networks and applications in vision. Proceedings of 2010 IEEE International Symposium on Circuits and Systems (ISCAS), 253–256. https://doi.org/10.1109/ISCAS.2010.5537907.

Pegler, G. F., & Ranieri, V. E. L. (2024). Ciência cidadã em áreas protegidas: boas práticas para formulação e implementação de projetos. Ambiente & Sociedade, 27, e01521. https://doi.org/10.1590/1809-4422asoc01521vu27L4AO. 

Pereira Ribeiro Teodoro, P. E., da Silva, R. M., da Silva, F. F., de Freitas, R. S., & de Oliveira Silva, A. (2024). Spectral discrimination of Eucalyptus species using artificial neural networks. Scientific Reports, 14(1). https://www.nature.com/articles/s41598-024-58242-0.

Reshi, A. A., Rustam, F., Mehmood, A., Alhossan, A., Alrabiah, Z., Ahmad, A., Alsuwailem, H., & Choi, G. S. (2021). An efficient CNN model for COVID‐19 disease detection based on X‐ray image classification. Complexity, 2021, Article 6621607. https://doi.org/10.1155/2021/6621607.

Royal Botanic Gardens, Kew. (2020). State of the world’s plants and fungi 2020. Royal Botanic Gardens, Kew. https://doi.org/10.34885/172

Russakovsky, O., Deng, J., Su, H., Krause, J., Satheesh, S., Ma, S., Huang, Z., Karpathy, A., Khosla, A., Bernstein, M., Berg, A. C., & Fei-Fei, L. (2015). ImageNet large scale visual recognition challenge. International Journal of Computer Vision, 115(3), 211–252. https://doi.org/10.1007/s11263-015-0816-y.

Tan, C., Sun, F., Kong, T., Zhang, W., Yang, C., & Liu, C. (2018). A survey on deep transfer learning. Lecture Notes in Computer Science, 11141, 270–279. https://doi.org/10.1007/978-3-030-01424-7_27.

Vinagreiro, M. A. L. (2022). Classificação baseada em espaços de camadas convolucionais de redes CNNs densas [Dissertação de Mestrado, Universidade de São Paulo]. Repositório Digital USP.

Wäldchen, J., & Mäder, P. (2018). Plant species identification using computer vision techniques: A systematic literature review. Archives of Computational Methods in Engineering, 25(2), 507–543. https://doi.org/10.1007/s11831-016-9206-z.

Yosinski, J., Clune, J., Bengio, Y., & Lipson, H. (2014). How transferable are features in deep neural networks? In Advances in Neural Information Processing Systems 27 (NIPS ’14) (pp. 3320–3328). NIPS Foundation.

