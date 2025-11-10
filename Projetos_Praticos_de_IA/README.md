# 🎯 Sistema de Avaliação de Currículos com IA

Sistema automatizado de avaliação de currículos implementado com **LangGraph** e **LLMs**, baseado nos critérios de avaliação da Gupy (manual divulgado por Gabriel Pontes).

## 📋 Visão Geral

Este projeto demonstra como modelos de linguagem grandes (LLMs) e fluxos de trabalho baseados em grafos podem ser combinados para criar um sistema sofisticado de avaliação de currículos, fornecendo análises consistentes e objetivas.

## ✨ Funcionalidades

O sistema avalia currículos com base em **4 critérios principais**:

1. **Experiências Profissionais e Acadêmicas** (30%)
   - Validação de campos obrigatórios
   - Nomenclaturas padrões de mercado
   - Responsabilidades e conquistas mensuráveis

2. **Idiomas** (20%)
   - Idiomas declarados
   - Níveis de proficiência

3. **Conquistas e Certificados** (30%)
   - Cursos e certificações
   - Trabalho voluntário
   - Competências (liderança, comunicação, etc.)

4. **Habilidades** (20%)
   - Mínimo de 30 habilidades técnicas e comportamentais
   - Habilidades desenvolvidas ao longo da carreira

## 🏗️ Arquitetura

### Componentes Principais

- **StateGraph**: Define o fluxo de trabalho do processo de avaliação
- **LLM (Claude 3.7 Sonnet)**: Análise semântica e compreensão de linguagem
- **Funções de Avaliação**: Módulos especializados para cada critério
- **Lógica Condicional**: Fluxo adaptativo baseado em pontuações intermediárias

### Fluxo de Avaliação

```
Experiências → Idiomas → Conquistas → Habilidades → Pontuação Final
     ↓            ↓           ↓            ↓
  (> 0.5)      (> 0.6)     (> 0.7)    (sempre)
     ↓            ↓           ↓            ↓
  Continua    Continua    Continua    Finaliza
     ou           ou          ou
  Finaliza    Finaliza    Finaliza
```

## 🚀 Tecnologias

- **Python 3.10+**
- **LangGraph** - Orquestração de workflows com LLMs
- **LangChain** - Framework para aplicações com LLMs
- **OpenRouter API** - Acesso a múltiplos modelos LLM
- **Claude 3.7 Sonnet** - Modelo de linguagem da Anthropic
- **python-dotenv** - Gerenciamento de variáveis de ambiente

## 📦 Instalação

1. Clone o repositório:
```bash
git clone https://github.com/rafaelnovaes22/repositorio.git
cd repositorio/Projetos_Praticos_de_IA
```

2. Instale as dependências:
```bash
pip install langgraph langchain-anthropic langchain-core python-dotenv
```

3. Configure as variáveis de ambiente:

Crie um arquivo `.env` na raiz do projeto:
```env
OPENROUTER_API_KEY=sua_chave_aqui
```

## 💻 Como Usar

1. Abra o notebook `avaliador_de_curriculo.ipynb`

2. Execute as células de configuração

3. Use a função `grade_curriculum()` para avaliar um currículo:

```python
resultado = grade_curriculum(seu_curriculo_texto)

print(f"Pontuação de Experiências: {resultado['experience_score']}")
print(f"Pontuação de Idiomas: {resultado['language_score']}")
print(f"Pontuação de Conquistas: {resultado['achievements_score']}")
print(f"Pontuação de Habilidades: {resultado['habilities_score']}")
print(f"Pontuação Final: {resultado['final_score']}")
```

## 🎯 Critérios de Avaliação

### Pesos das Pontuações

| Critério | Peso | Threshold |
|----------|------|-----------|
| Experiências | 30% | > 0.5 |
| Idiomas | 20% | > 0.6 |
| Conquistas | 30% | > 0.7 |
| Habilidades | 20% | - |

**Pontuação Final** = (Experiências × 0.3) + (Idiomas × 0.2) + (Conquistas × 0.3) + (Habilidades × 0.2)

## 🔍 Exemplo de Uso

O notebook inclui um currículo de exemplo completo para demonstração do sistema.

## 📊 Benefícios

- ✅ **Consistência**: Avaliações objetivas e padronizadas
- ✅ **Eficiência**: Análise automatizada em segundos
- ✅ **Escalabilidade**: Processa múltiplos currículos simultaneamente
- ✅ **Transparência**: Pontuações detalhadas por critério
- ✅ **Adaptabilidade**: Fluxo condicional baseado em qualidade

## 🤝 Contribuindo

Contribuições são bem-vindas! Sinta-se à vontade para:

- Reportar bugs
- Sugerir novas funcionalidades
- Melhorar a documentação
- Enviar pull requests

## 📝 Licença

Este projeto foi baseado no repositório original Projetos Práticos de IA da Scoras Academy.
- GitHub: [@Scoras-Academy]https://github.com/Scoras-Academy/Projetos_Praticos_de_IA

## 👤 Autor

**Rafael de Novaes**
- LinkedIn: [rafaeldenovaes](https://www.linkedin.com/in/rafaeldenovaes/)
- GitHub: [@rafaelnovaes22](https://github.com/rafaelnovaes22)

## 🙏 Agradecimentos

- Baseado nos critérios de avaliação da Gupy (manual de Gabriel Pontes)
- Desenvolvido durante o curso de Engenharia de IA na Scoras Academy
- Agradecimento especial ao professor Anderson Amaral e comunidade da Scoras Academy pelo suporte e conhecimento compartilhado
- Inspirado pelas melhores práticas de recrutamento e seleção do mercado brasileiro

---

⭐ Se este projeto foi útil para você, considere dar uma estrela no repositório!