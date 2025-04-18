# Importa a biblioteca pikepdf para manipulação de arquivos PDF protegidos por senha
import pikepdf
# Importa tqdm para exibir uma barra de progresso durante a execução
from tqdm import tqdm

# Caminho do arquivo PDF protegido por senha
# Substitua 'seu_caminho_para_o_pdf' pelo caminho completo do arquivo PDF que deseja testar
pdf_file = "seu_caminho_para_o_pdf"

# Caminho do arquivo de lista de senhas (wordlist)
# Substitua 'seu_caminho_para_a_wordlist' pelo caminho completo do arquivo de texto contendo as senhas
wordlist = "seu_caminho_para_a_wordlist"

# Função para realizar ataque de força bruta em um arquivo PDF
def brute_force_pdf(pdf_path, wordlist_path):
    """
    Tenta abrir um arquivo PDF protegido por senha usando uma lista de senhas.
    
    Args:
        pdf_path (str): Caminho para o arquivo PDF.
        wordlist_path (str): Caminho para o arquivo de lista de senhas.
    
    Returns:
        str: A senha encontrada, ou None se nenhuma senha funcionar.
    """
    # Abre o arquivo de lista de senhas e lê todas as senhas em uma lista
    with open(wordlist_path, "r", encoding="latin-1") as file:
        passwords = [line.strip() for line in file]  # Remove espaços em branco e quebras de linha

    # Itera sobre cada senha na lista, exibindo uma barra de progresso
    for password in tqdm(passwords, desc="Tentando senhas..."):
        try:
            # Tenta abrir o PDF com a senha atual
            with pikepdf.open(pdf_path, password=password):
                # Se a senha estiver correta, exibe uma mensagem de sucesso
                print(f"\n[SUCCESS] Senha encontrada: '{password}'")
                return password  # Retorna a senha encontrada
        except pikepdf.PasswordError:
            # Se a senha estiver errada, continua para a próxima
            continue
        except Exception as e:
            # Captura outros erros inesperados e exibe uma mensagem
            print(f"\n[ERRO inesperado] {e}")
            break  # Interrompe o loop em caso de erro inesperado

    # Se nenhuma senha funcionar, exibe uma mensagem de falha
    print("\n[FAIL] Nenhuma senha da lista funcionou.")
    return None  # Retorna None se nenhuma senha for encontrada

# Ponto de entrada do script
if __name__ == "__main__":
    # Chama a função de força bruta com os caminhos especificados
    brute_force_pdf(pdf_file, wordlist)
