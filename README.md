
import hashlib

def simulate_attack():
    legit_code = "exec_nsu_sovereign_v1"
    malicious_code = "exec_nsu_sovereign_v1_HACKED"
    
    print("--- NSU STRESS TEST (LSS-Ω™) ---")
    print(f"[*] Validando código original: {legit_code}")
    legit_hash = hashlib.sha256(legit_code.encode()).hexdigest()
    print(f"[#] Hash Gerado: {legit_hash}")

    print("\n[!] Tentando injeção de bit malicioso...")
    malicious_hash = hashlib.sha256(malicious_code.encode()).hexdigest()
    
    if malicious_hash == legit_hash:
        print("\n🚨 SUCESSO: A física do SHA-256 foi burlada. O sistema morreu.")
    else:
        print(f"\n🛡️ STATUS: [BLOCK] - Hash divergente: {malicious_hash}")
        print(">>> A estrutura permanece íntegra. A mentira foi detectada.")

if __name__ == "__main__":
    simulate_attack()
