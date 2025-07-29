# DEEP-FLORA

Deep-Flora é um sistema simples e de fácil acesso projetado para reconhecer automaticamente uma ampla variedade de espécies de plantas a partir de imagens. A proposta é contribuir com áreas como botânica, agricultura e estudos ambientais, oferecendo uma ferramenta acessível para identificação precisa de espécies.

A motivação do projeto surge do desafio recorrente na identificação de espécies, dada a vasta biodiversidade e a semelhança morfológica entre muitas plantas. A proposta do Deep-Flora é democratizar o acesso a esse tipo de conhecimento utilizando redes neurais convolucionais (CNNs), aprendizado profundo (Deep Learning) e transferência de aprendizado (Transfer Learning), treinadas com grandes bases públicas de dados, como Pl@ntNet-300K e GBIF.

# Metodologia
O pipeline completo foi desenvolvido em Python e estruturado para garantir reprodutibilidade e desempenho. As principais etapas são:

### Coleta e curadoria de dados
- Coleta automatizada via API (GBIF) e download do dataset Pl@ntNet-300K.
- Filtro por imagens do tipo stillimage e resolução mínima de 720×720 pixels, para a API.
- Exclusão de imagens corrompidas, duplicadas e de herbário.
- Curadoria final resultou em 540.353 imagens de 487 espécies.

### Pré-processamento
- Conversão para RGB e redimensionamento.
- Normalização conforme as exigências das arquiteturas (ImageNet).
- Divisão em treino (70%), validação (15%) e teste (15%).

### Data augmentation
- Aplicado apenas ao conjunto de treino com:
- Rotação até 30º
- Flip horizontal e vertical
- Cisalhamento
- Ajustes de brilho e contraste

### Modelos utilizados
- ResNet-50 e EfficientNet-B3 com pesos do ImageNet.
- Cabeçalho adaptado para 487 classes.
- Congelamento inicial do backbone por 3 épocas, seguido de fine-tuning.
- Treinamento com:
  - batch_size = 32
  - learning_rate = 0.0001
  - epochs = 9 para o modelo EfficientNet-B3 e 10 para o modelo ResNet-50.
  - Otimizador Adam
  - Scheduler StepLR (step_size=5, gamma=0.1)

### Infraestrutura
- Sistema: Windows 11 + CUDA 11.8
- GPU: NVIDIA GTX 1650 (4 GB)
- Bibliotecas principais: PyTorch, torchvision, scikit-learn, pandas, pillow, opencv, Flask

# Resultados 
Todos os resultados gerados ao longo do experimento foram organizados em arquivos tabulares, permitindo a verificação detalhada das métricas e análises de desempenho. Esses arquivos estão disponíveis na pasta [results](results) e parte das análises também pode ser visualizada diretamente no Jupyter Notebook principal, disponível em [analise_results_resnet50.ipynb](analise_results_resnet50.ipynb).

Após os testes com ambos os modelos — ResNet-50 e EfficientNet-B3 — os seguintes resultados globais foram obtidos:
<p align="center"> <img width="736" height="93" alt="Resultados ResNet vs EfficientNet" src="https://github.com/user-attachments/assets/c4d3976f-5cc8-433f-b03d-f19f21660fad" /> </p>

Embora a EfficientNet-B3 tenha gerado um modelo consideravelmente mais leve em termos de armazenamento, a ResNet-50 apresentou desempenho superior nas principais métricas de classificação, como acurácia, f1-score macro e recall ponderado, sendo, portanto, a arquitetura selecionada para integrar a versão final do sistema.

Todo o sistema pode ser encontrado em (https://github.com/Hosamuel/classifique-render.git) e pode ser ultilizado de forma local.
# Referências
Baumbach, L., Schmidt, C., & Michalik, A. (2019). Big data and citizen science—An integration towards data-driven sustainable development. Sustainability, 11(4), 956. https://doi.org/10.3390/su11040956.

BFG – The Brazil Flora Group. (2018). Brazilian Flora 2020: Innovation and collaboration to meet Target 1 of the Global Strategy for Plant Conservation. Rodriguésia, 69(4), 1513–1527. https://doi.org/10.1590/2175-7860201869402.

Chen, Y., Huang, Y., Zhang, Z., Wang, Z., Liu, B., Liu, C., Huang, C., Dong, S., Pu, X., Wan, F., Qiao, X., & Qian, W. (2023). Plant image recognition with Deep Learning: A review. Computers and Electronics in Agriculture, 212, 108072. https://doi.org/10.1016/j.compag.2023.108072.

Garcin, C., Joly, A., Bonnet, P., Servajean, M., & Salmon, J. (2021). Pl@ntNet-300K image dataset (1.0) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.4726653.

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

