# Soberania
import hashlib
import time

# O DESAFIO DO ARQUITETO
# Tente alterar o 'MALICIOUS_CODE' e fazer o 'core.py' aceitar.
# Se o hash mudar, a estrutura bloqueia.

def simulate_attack():
    legit_code = "exec_nsu_sovereign_v1"
    malicious_code = "exec_nsu_sovereign_v1_HACKED"
    
    print("--- NSU STRESS TEST ---")
    print(f"Calculando integridade do código legítimo...")
    legit_hash = hashlib.sha256(legit_code.encode()).hexdigest()
    
    print(f"Tentando injetar bit malicioso...")
    malicious_hash = hashlib.sha256(malicious_code.encode()).hexdigest()
    
    if malicious_hash == legit_hash:
        print("🚨 SUCESSO: Você burlou a física do SHA-256!")
    else:
        print("🛡️ STATUS: BLOCK. A estrutura permanece íntegra.")

if __name__ == "__main__":
    simulate_attack()
