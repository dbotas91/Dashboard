---
tags:
  - elearning
dg-publish: "true"
dg-note-icon: lackluster
noteIcon: lackluster
---
# Python e R no jupyter notebook

- [https://dzone.com/articles/using-r-on-jupyternbspnotebook](https://dzone.com/articles/using-r-on-jupyternbspnotebook)

- [https://irkernel.github.io/](https://irkernel.github.io/)

- [https://anderfernandez.com/en/blog/how-to-program-with-python-and-r-in-the-same-jupyter-notebook/](https://anderfernandez.com/en/blog/how-to-program-with-python-and-r-in-the-same-jupyter-notebook/)

- [https://dzone.com/articles/using-r-on-jupyternbspnotebook](https://dzone.com/articles/using-r-on-jupyternbspnotebook)

[

How to Add R to Jupyter Notebook (full steps)

You can add R to Jupyter Notebook by typing this command in the Anaconda Prompt: conda install -c r r-irkernel But just in case you were wondering, here are the full steps to add R to Jupyter Notebook from scratch.

![](https://datatofish.com/wp-content/uploads/2018/05/64-1-1.png)https://datatofish.com/r-jupyter-notebook/

![](https://datatofish.com/wp-content/uploads/2020/01/002_add_r_to_jupyter.png)](https://datatofish.com/r-jupyter-notebook/)

[

https://www.datacamp.com/community/blog/jupyter-notebook-r



](https://www.datacamp.com/community/blog/jupyter-notebook-r)

```Python
Para gerar a sequência de Fibonacci em Python, você pode usar o seguinte código:

# Definir uma função para gerar a sequência de Fibonacci
def fibonacci(n):
  # Inicializar as duas primeiras variáveis da sequência
  a = 0
  b = 1
  # Criar uma lista vazia para armazenar os termos da sequência
  lista = []
  # Usar um laço for para iterar n vezes
  for i in range(n):
    # Adicionar o valor de a à lista
    lista.append(a)
    # Atualizar os valores de a e b usando a regra de Fibonacci
    a, b = b, a + b
  # Retornar a lista com os termos da sequência
  return lista

# Testar a função com um exemplo
print(fibonacci(10))
```