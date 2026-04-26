# Comparação geral dos 4 datasets
## Posicionamento como Proxy

| Critério | AmazonCat-13K | Eurlex-4K | Amazon-670K | Wiki10-31K |
|---|---|---|---|---|
| Cardinalidade média | 5,04 — baixa | 5,32 — baixa | 5,45 — baixa | 18,64 — alta |
| Cauda longa | Moderada (20,8% ≤5 pts) | Moderada (48,4% ≤5 pts) | Extrema (83,3% ≤5 pts) | Alta (80,4% ≤5 pts) |
| Zero-shot no teste | **0,0%** | 6,4% | 0,8% | 4,5% |
| Features ativas/ponto (mediana) | 45 (muito esparso) | 144 (moderado) | 48 (muito esparso) | 520 (moderado) |
| Pontos/label (média) | 448,57 (bem representado) | 21,80 | 4,01 | 8,81 |
| Domínio | E-commerce | Jurídico (EU) | E-commerce | Enciclopédico |
| Texto bruto disponível | Sim (descrições + reviews) | Não (somente BoW) | Sim (JSONL) | Não (somente BoW) |
| Embeddings pré-computados | Sim (3 sentence-transformers) | Não | Não | Não |

O AmazonCat-13K é o dataset **mais favorável** para modelagem entre os quatro: zero-shot nulo, cauda longa menos severa, labels bem representadas e embeddings já disponíveis. Como proxy, é adequado para problemas de classificação de texto em domínio comercial com cardinalidade baixa a moderada.
