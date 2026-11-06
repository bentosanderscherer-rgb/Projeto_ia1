# Avaliação Técnica - Contraturno IA 

1. C. Uma string (texto)
2.A API deve ficar no arquivo .env para proteger informações importantes, como a chave de acesso. Assim, ela não fica exposta diretamente no código.
3.B. Uma lista de dicionários.
4.total = 0
while True:
    n = int(input("Número (0 para sair): "))
    if n == 0:
        break
    total += n

print(f"Soma: {total}")
5.a) Porque o chat sem histórico não guarda as mensagens anteriores. Assim, o modelo não consegue lembrar o nome informado.

  b) Devemos adicionar o histórico de conversas ao código, usando uma lista de dicionários com role e content, para o modelo receber as mensagens anteriores.
  
  6.b)
  7.def carregar_contexto(caminho: str = "contexto.txt") -> str: try: with open(caminho, encoding="utf-8") as arquivo: texto = arquivo.read().strip() except FileNotFoundError: print(f"Aviso: arquivo '{caminho}' não encontrado. Seguindo sem contexto.") return ""
  8.import streamlit as st

if "historico" not in st.session_state:
    st.session_state.historico = []

pergunta = st.chat_input("Digite...")

if pergunta:
    st.session_state.historico.append(
        {"role": "user", "content": pergunta}
    )

    b)Usamos st.session_state porque ele mantém os dados guardados entre os cliques e atualizações da página. Já uma variável comum pode ser reiniciada quando o Streamlit executa o código novamente.
