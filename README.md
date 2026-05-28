# ⚡ Split Energy

Monitor inteligente de consumo de energia para pequenos e médios comércios.

## 📋 Sobre o projeto

O Split Energy nasceu de uma pesquisa com gestores comerciais que revelou um problema central: **a maioria dos comerciantes suspeita que desperdiça energia, mas não tem como identificar onde nem como agir**.

A solução é um sistema web simples, sem instalação de hardware, que permite ao gestor lançar a conta de luz mensal, cadastrar os aparelhos do estabelecimento e descobrir exatamente onde o dinheiro está sendo gasto — e quanto está "vazando" sem explicação.

---

## 🎯 Público-alvo

Pequenos e médios comércios com consumo de energia relevante no custo operacional:

- Restaurantes e lanchonetes
- Padarias
- Lavanderias
- Clínicas e consultórios
- Academias

---

## ✅ Funcionalidades

### Essenciais (implementadas)
- [x] Cadastro de empresas com tarifa de energia
- [x] Lançamento mensal de fatura (valor, tarifa, período em dias)
- [x] Cadastro de aparelhos com potência (W) e horas de uso/dia
- [x] Cálculo automático do custo estimado por aparelho
- [x] Comparação entre fatura real e consumo estimado
- [x] Diagnóstico automático da diferença (consumo não identificado, dentro do estimado, exato)

### Importantes (implementadas)
- [x] Ranking visual de aparelhos por custo com barra proporcional
- [x] Prévia em tempo real do custo acumulado ao adicionar aparelhos
- [x] Sugestão automática de economia no aparelho mais caro
- [x] Alerta destacado quando diferença ultrapassa 15%
- [x] Histórico de meses por empresa (salvo localmente)
- [x] Gráfico de evolução dos últimos 6 meses
- [x] Projeção da próxima conta com base no histórico
- [x] Exportação/impressão do resultado em PDF

### Extras (implementadas)
- [x] Relatório ESG com emissão de CO₂, equivalente em km de carro e árvores para compensação
- [x] Custo energético por operação (ex: custo por pizza, por atendimento, por lavagem)

---

## 🚀 Como usar

O Split Energy é um arquivo HTML único. **Não requer instalação, servidor ou internet após o carregamento.**

### Rodando localmente

1. Baixe o arquivo `split-energy-mvp.html`
2. Abra no navegador (Chrome ou Edge recomendados)
3. Pronto — o sistema já está funcionando

### Publicando online (opcional)

Para compartilhar com outras pessoas via link:

1. Acesse [tiiny.host](https://tiiny.host)
2. Arraste o arquivo `split-energy-mvp.html`
3. Copie o link gerado — sem cadastro, gratuito

---

## 💾 Armazenamento de dados

Os dados (empresas, histórico de meses, aparelhos) são salvos no **localStorage do navegador** — armazenamento local da máquina, sem envio para nenhum servidor.

> ⚠️ Os dados ficam salvos no navegador da máquina utilizada. Limpar os dados do navegador apaga o histórico do sistema.

---

## 🧮 Como os cálculos funcionam

### Custo estimado por aparelho

```
kWh = (Potência em W ÷ 1000) × Horas de uso por dia × Dias do período
Custo = kWh × Tarifa (R$/kWh)
```

### Diferença (consumo não identificado)

```
Diferença = Valor real da fatura − Soma do custo estimado de todos os aparelhos
```

- **Positivo** → há consumo na fatura que os aparelhos cadastrados não explicam
- **Negativo** → o estimado supera a fatura (aparelhos usados menos do que informado)
- **Zero** → consumo totalmente explicado pelos aparelhos

### Emissão de CO₂ (Relatório ESG)

```
CO₂ (kg) = kWh total × 0,0817
```

> Fator de emissão médio da rede elétrica brasileira — MCTIC 2023

### Custo por operação

```
Custo por operação = Custo estimado total ÷ Número de operações no mês
```

---

## 🛠️ Stack tecnológica

| Tecnologia | Função | Custo |
|---|---|---|
| HTML + CSS | Interface e estilos | Gratuito |
| React 18 (via CDN) | Componentes e estado | Gratuito |
| Babel Standalone | Transpilação JSX no browser | Gratuito |
| localStorage | Persistência de dados | Gratuito |
| Google Fonts (Syne + DM Sans) | Tipografia | Gratuito |

> Nenhuma dependência instalada via npm. Nenhum servidor necessário.

---

## 👥 Equipe

Projeto desenvolvido por alunos do curso de **Análise e Desenvolvimento de Sistemas** — Senac Joinville.

---

## 📄 Licença

Projeto acadêmico. Uso livre para fins educacionais.