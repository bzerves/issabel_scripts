def criar_tronco():
# Coleta as informações do tronco SIP
nome_do_peer = input("Nome do peer SIP: ")
host = input("Endereço IP ou nome do host: ")
usuario = input("Usuário SIP: ")
senha = input("Senha SIP: ")

# Escreve o arquivo de configuração do tronco SIP
with open("sip_peer.conf", "w") as f:
    f.write(f"[{nome_do_peer}]\n")
    f.write("type=peer\n")
    f.write(f"host={host}\n")
    f.write(f"username={usuario}\n")
    f.write(f"secret={senha}\n")

criar_novo_tronco = input("Deseja criar um novo tronco (s/n)? ")

if criar_novo_tronco.lower() == "s":
    criar_tronco()

import string
import random

def gerar_senha():
    letras = string.ascii_letters + string.digits + string.punctuation
    return ''.join(random.choice(letras) for i in range(20))

def criar_ramal():
    # Coleta as informações do ramal
    nome_do_ramal = input("Nome do ramal: ")
    senha_do_ramal = gerar_senha()

    # Escreve o arquivo de configuração do ramal
    with open("ramal.conf", "w") as f:
        f.write(f"[{nome_do_ramal}]\n")
        f.write(f"secret={senha_do_ramal}\n")
        f.write("type=friend\n")
        f.write("context=interno\n")
        f.write("host=dynamic\n")

    print("A senha gerada para o ramal é:", senha_do_ramal)

criar_novo_ramal = input("Deseja criar um novo ramal (s/n)? ")

if criar_novo_ramal.lower() == "s":
    criar_ramal()

# Coleta as informações da rota de entrada
nome_da_rota_entrada = input("Nome da rota de entrada: ")
nome_do_peer_entrada = input("Nome do peer SIP para a rota de entrada: ")

# Escreve o arquivo de configuração da rota de entrada
with open("entrada.conf", "w") as f:
    f.write(f"[{nome_da_rota_entrada}]\n")
    f.write("exten => _X.,1,Dial(SIP/{nome_do_peer_entrada})\n")

# Coleta as informações da rota de saída
nome_da_rota_saida = input("Nome da rota de saída: ")
nome_do_peer_saida = input("Nome do peer SIP para a rota de saída: ")

# Escreve o arquivo de configuração da rota de saída
with open("saida.conf", "w") as f:
    f.write(f"[{nome_da_rota_saida}]\n")
    f.write("exten => _X.,1,Dial(SIP/{nome_do_peer_saida})\n")
