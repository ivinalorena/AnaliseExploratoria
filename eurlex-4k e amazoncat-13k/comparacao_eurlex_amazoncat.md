# Análise Comparativa: Eurlex-4K vs AmazonCat-13K

---

## 1. Estatísticas Gerais

| Atributo | Eurlex-4K | AmazonCat-13K |
|---|---|---|
| Documentos (treino) | 15.511 | 1.186.239 |
| Documentos (teste) | 3.803 | 306.782 |
| Features (dimensões) | 5.000 | 203.882 |
| Labels únicas (total possível) | 3.993 | 13.330 |
| Labels únicas observadas (treino) | 3.786 | 13.330 |
| Labels/ponto — média | 5,32 | 5,04 |
| Labels/ponto — mediana | 6 | 4 |
| Labels/ponto — desvio padrão | 1,35 | 3,52 |
| Labels/ponto — máximo | 24 | 57 |
| Pontos/label (média) | 21,80 | 448,57 |
| Densidade matriz Y (%) | 0,13325 | 0,03781 |
| Sparsidade Y | 99,867% | 99,962% |
| Sparsidade X | 95,256% | 99,965% |

---

## 2. Cardinalidade (Labels por Ponto)

| Percentil | Eurlex-4K | AmazonCat-13K |
|---|---|---|
| p25 | 5 | 3 |
| p50 (mediana) | 6 | 4 |
| p75 | 6 | 6 |
| p90 | 6 | 9 |
| p95 | 7 | 12 |
| p99 | 9 | 19 |


---

## 3. Cauda Longa de Labels

| Faixa | Eurlex-4K | AmazonCat-13K |
|---|---|---|
| Labels sem ocorrência no treino | 207 (5,2%) | 0 (0,0%) |
| Labels com exatamente 1 ponto | 722 (18,1%) | 753 (5,6%) |
| Labels com até 5 pontos | 1.933 (48,4%) | 2.768 (20,8%) |
| Labels com até 10 pontos | — | 4.181 (31,4%) |
| Labels com até 100 pontos | — | 9.764 (73,2%) |
| Labels com 10+ pontos | 1.398 (35,0%) | 9.394 (70,5%) |
| Labels com 100+ pontos | 185 (4,6%) | 3.581 (26,9%) |
| Labels com 1.000+ pontos | 1 (0,0%) | 719 (5,4%) |


---

## 4. Cobertura Treino / Teste (Zero-Shot)

| Métrica | Eurlex-4K | AmazonCat-13K |
|---|---|---|
| Labels únicas no treino | 3.786 | 13.330 |
| Labels únicas no teste | 2.673 | 13.275 |
| Labels cobertas pelo treino | 2.503 (93,6%) | 13.275 (100,0%) |
| Labels zero-shot no teste | 170 (6,4%) | 0 (0,0%) |



---

## 5. Esparsidade das Features

| Estatística | Eurlex-4K | AmazonCat-13K |
|---|---|---|
| Média de features ativas/ponto | 237,2 | 71,2 |
| Mediana de features ativas/ponto | 144 | 45 |
| Máximo | 2.593 | 2.113 |
| p25 | 88 | 22 |
| p75 | 287 | 91 |
| p90 | 534 | 159 |
| p99 | 1.204 | 383 |
| Sparsidade X | 95,256% | 99,965% |

---

## 6. Caracterização das Features

| Evidência | Eurlex-4K | AmazonCat-13K |
|---|---|---|
| Valores negativos | 0 | 0 |
| Valores inteiros | 0 (0,0%) | 6,1% |
| Mínimo dos valores | 0,016911 | 1,000000 |
| Máximo dos valores | 8.244,748 | 2.952,327 |
| Mediana dos valores | 3,5286 | 7,4263 |
| p99 dos valores | 108,36 | 78,92 |
| Tipo inferido | TF-IDF | TF-IDF |


---

## 7. Síntese Comparativa

| Critério | Eurlex-4K | AmazonCat-13K |
|---|---|---|
| Escala | Pequeno (15k treino) | Grande (1,2M treino) |
| Cardinalidade | Baixa e concentrada (std=1,35) | Baixa e variável (std=3,52) |
| Cauda longa | Moderada (48,4% ≤5 pts) | Leve (20,8% ≤5 pts) |
| Zero-shot | 6,4% — teto estrutural presente | 0,0% — sem teto estrutural |
| Densidade de features | Moderada (mediana=144 ativas) | Muito esparso (mediana=45 ativas) |
| Representação disponível | Somente TF-IDF | TF-IDF + 3 embeddings pré-computados |
| Texto bruto | Não | Sim (descrições + reviews) |
| Domínio | Jurídico (documentos EU) | Comercial (produtos Amazon) |
| Favorabilidade para modelagem | Moderada | Alta |

### Quando usar cada um como proxy

**Eurlex-4K** é mais adequado quando o problema real envolve vocabulário controlado, domínio especializado, categorização hierárquica e volume moderado de dados. O zero-shot de 6,4% precisa ser comunicado explicitamente ao reportar resultados.

**AmazonCat-13K** é mais adequado quando o problema real é de texto comercial ou geral, com cardinalidade variável e necessidade de comparar representações esparsas vs. densas. A cobertura total e a boa representação das labels tornam os resultados mais interpretáveis e as comparações entre modelos mais justas.
