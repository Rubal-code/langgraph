# LangGraph Learning Repository

A comprehensive collection of Jupyter notebooks demonstrating LangGraph workflows, from basic computations to advanced multi-agent orchestration patterns.

## 📋 Overview

This repository provides hands-on examples of building AI workflows using LangGraph, LangChain's powerful graph-based orchestration framework. It covers essential concepts including sequential workflows, parallel processing, conditional logic, and complex agent interactions.

## 🎯 What is LangGraph?

LangGraph is a library for building stateful, agentic applications with LLMs. It allows you to:
- Define complex workflows using a graph-based architecture
- Manage state across multiple agents and tools
- Build loops and conditional branching logic
- Implement both synchronous and asynchronous workflows
- Create reusable, composable workflow components

## 📚 Repository Structure

### Notebooks Included

| Notebook | Description | Level |
|----------|-------------|-------|
| **1_bmi_calculator.ipynb** | Calculate Body Mass Index using a simple workflow | Beginner |
| **2_simple_llm_workflow_code.ipynb** | Build a basic LLM workflow for text processing | Beginner |
| **3_simple_parallel_workflow.ipynb** | Execute multiple tasks in parallel | Intermediate |
| **3_1_upsc_llm_parallel_workflow.ipynb** | Real-world example: UPSC exam preparation with parallel workflows | Intermediate |
| **4_conditional_workflow.ipynb** | Implement conditional branching and decision logic | Intermediate |

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- Jupyter Notebook or JupyterLab
- Basic understanding of Python and LLMs

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Rubal-code/langgraph.git
   cd langgraph
   ```

2. **Install dependencies:**
   ```bash
   pip install langgraph langchain python-dotenv jupyter
   ```

3. **Install LLM provider SDK (if needed):**
   ```bash
   # For OpenAI
   pip install openai

   # For Anthropic Claude
   pip install anthropic

   # For other providers, check LangChain documentation
   ```

4. **Set up environment variables:**
   ```bash
   cp .env.example .env
   # Edit .env with your API keys
   ```

5. **Launch Jupyter:**
   ```bash
   jupyter notebook
   ```

## 📖 Learning Path

Follow this recommended progression to master LangGraph:

### Phase 1: Fundamentals
1. Start with **1_bmi_calculator.ipynb** to understand basic workflow concepts
2. Move to **2_simple_llm_workflow_code.ipynb** to learn LLM integration

### Phase 2: Advanced Concepts
3. Explore **3_simple_parallel_workflow.ipynb** for parallel execution patterns
4. Study **3_1_upsc_llm_parallel_workflow.ipynb** for real-world applications
5. Master **4_conditional_workflow.ipynb** for complex decision logic

## 🔑 Key Concepts Covered

### Sequential Workflows
Learn how to chain operations linearly, where each step depends on the output of the previous step.

### Parallel Workflows
Execute multiple independent tasks simultaneously to improve performance and efficiency.

### Conditional Logic
Implement branching logic where workflow paths diverge based on conditions or decisions.

### State Management
Understand how LangGraph manages and passes state through workflow nodes.

### LLM Integration
Integrate language models into your workflows for intelligent decision-making and text generation.

## 💡 Use Cases

This repository demonstrates workflows suitable for:
- **Educational Applications**: UPSC exam preparation, course planning
- **Data Processing**: Multi-stage data transformation pipelines
- **Customer Service**: Intelligent routing and decision workflows
- **Content Generation**: Parallel content creation and analysis
- **Research Assistants**: Complex multi-step research workflows

## 🛠️ Workflow Architecture

Each notebook follows this general architecture:

```
Input
  ↓
[Node 1] → (Conditional Router) → [Node 2A] ⟷ [Node 2B] (Parallel)
  ↓                                   ↓           ↓
[Node 3] ← ← ← ← ← ← ← ← ← ← ← ← ← ← ← ← ← ← ← ←
  ↓
Output
```

## 📚 Common Patterns

### Pattern 1: Sequential Processing
```python
graph.add_node("step1", process_step1)
graph.add_node("step2", process_step2)
graph.add_edge("step1", "step2")
```

### Pattern 2: Parallel Execution
```python
graph.add_node("task_a", execute_task_a)
graph.add_node("task_b", execute_task_b)
graph.add_node("merge", merge_results)

graph.add_edge("start", "task_a")
graph.add_edge("start", "task_b")
graph.add_edge("task_a", "merge")
graph.add_edge("task_b", "merge")
```

### Pattern 3: Conditional Routing
```python
def router(state):
    if state["condition"]:
        return "path_a"
    return "path_b"

graph.add_conditional_edges("decision", router, {
    "path_a": "node_a",
    "path_b": "node_b"
})
```

## 🔗 Resources

- [LangGraph Official Documentation](https://langchain-ai.github.io/langgraph/)
- [LangChain Documentation](https://python.langchain.com/)
- [LangGraph GitHub Repository](https://github.com/langchain-ai/langgraph)
- [Agentic AI Design Patterns](https://www.anthropic.com/research)

## 🤝 Contributing

Contributions are welcome! Please feel free to:
- Add more workflow examples
- Improve existing notebooks with clearer explanations
- Fix bugs or add features
- Submit pull requests

To contribute:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit changes (`git commit -m 'Add your feature'`)
4. Push to branch (`git push origin feature/your-feature`)
5. Open a Pull Request

## ⚠️ Prerequisites & Setup Notes

### API Keys Required
Most notebooks will require API keys for LLM providers:
- **OpenAI**: Set `OPENAI_API_KEY` environment variable
- **Anthropic**: Set `ANTHROPIC_API_KEY` environment variable
- Check individual notebooks for specific requirements

### Jupyter Environment
These notebooks are designed to work with:
- Jupyter Notebook (recommended)
- JupyterLab
- VS Code with Jupyter extension
- Google Colab (with minor adjustments)

## 📝 Notebook Structure

Each notebook typically includes:
1. **Imports & Setup**: Required libraries and configuration
2. **Problem Statement**: Clear description of what the workflow solves
3. **Implementation**: Step-by-step code with explanations
4. **Execution**: Running the workflow with sample inputs
5. **Analysis**: Results and insights from the execution
6. **Exercises**: Optional challenges to deepen understanding

## 🐛 Troubleshooting

**Issue**: ImportError for langgraph
- **Solution**: Ensure LangGraph is installed: `pip install langgraph --upgrade`

**Issue**: API key errors
- **Solution**: Verify API keys are set in environment variables or `.env` file

**Issue**: Notebook kernel issues
- **Solution**: Restart the kernel and re-run all cells in sequence

For more help, check the LangGraph documentation or open an issue in the repository.

## 📊 Workflow Complexity Levels

| Notebook | Nodes | Edges | Conditionals | Parallel Tasks |
|----------|-------|-------|--------------|----------------|
| BMI Calculator | 2-3 | Sequential | No | No |
| Simple LLM | 3-4 | Sequential | No | No |
| Parallel Workflow | 4+ | Mixed | No | Yes |
| UPSC Workflow | 5+ | Mixed | No | Yes |
| Conditional Workflow | 5+ | Mixed | Yes | Yes |

## 📄 License

This repository is open source and available under the MIT License. See LICENSE file for details.

## 👤 Author

Created by [Rubal-code](https://github.com/Rubal-code)

## 🙏 Acknowledgments

- LangChain and LangGraph teams for the excellent frameworks
- The open-source community for feedback and contributions
- All contributors and users who help improve this repository

## 📞 Support & Contact

- Open an issue for bug reports or feature requests
- Check existing issues before creating a new one
- Include code snippets and error messages in issue descriptions

## 🔄 Version History

- **v1.0** (Current): Initial release with 5 core notebooks covering fundamental to intermediate LangGraph concepts

---

**Happy Learning! 🎉** Start with the BMI calculator and progress through the notebooks to become proficient in building sophisticated LangGraph workflows.
