# PROJETO-FLUTTER-
# 🧮 Calculadora Universal — Flutter & Dart

Projeto Flutter com duas calculadoras integradas em um único app: uma **Calculadora Universal** extensível via dicionário de funções, e uma **Calculadora de Raízes** para equações de 1.º e 2.º grau.

---

## 📱 Funcionalidades

### 1. Calculadora Universal
- Dicionário de funções (`Map<String, Function>`) que serve como motor de cálculo
- Suporte a **17 funções** organizadas em categorias:
  - **Básicas** — somar, subtrair, multiplicar, dividir
  - **Matemática** — potência, raiz, módulo, absoluto, fatorial
  - **Trigonometria** — seno, cosseno, tangente (em graus)
  - **Logaritmos** — log (base 10), ln (natural)
  - **Estatística** — média, máximo, mínimo
- Aceita múltiplos parâmetros separados por vírgula, espaço ou ponto-e-vírgula
- **Facilmente expansível**: basta adicionar uma nova entrada ao Map

### 2. Calculadora de Raízes
- Identifica automaticamente se a equação é de **1.º ou 2.º grau**
- Calcula raízes reais com a fórmula de Bhaskara
- Exibe o **discriminante (Δ)** e classifica o resultado:
  - Duas raízes reais distintas (Δ > 0)
  - Raiz dupla (Δ = 0)
  - Sem raízes reais (Δ < 0)
  - Uma raiz (1.º grau)
- Mostra o **passo a passo** da resolução

---

## 🗂️ Estrutura dos arquivos

```
├── lib/
│   └── main.dart              # App Flutter completo (UI + lógica)
├── calculator_logic.dart      # Lógica pura Dart (sem dependência Flutter)
└── README.md
```

---

## 🚀 Como executar

**Pré-requisitos:** Flutter SDK instalado ([flutter.dev](https://flutter.dev))

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/calculadora-universal.git
cd calculadora-universal

# Instale as dependências
flutter pub get

# Execute o app
flutter run
```

---

## 🔧 Como expandir a Calculadora Universal

Para adicionar uma nova função, basta inserir uma entrada no Map `calculatorFunctions` em qualquer ponto do código — inclusive em tempo de execução:

```dart
calculatorFunctions['percentual'] = (params) {
  _check('percentual', params, exato: 2);
  return (params[0] * params[1]) / 100;
};

// Uso:
calcular('percentual', [200.0, 15.0]); // → 30.0
```

Nenhuma outra parte do código precisa ser modificada.

---

## 📐 Exemplos de uso (Dart puro)

```dart
// Calculadora Universal
calcular('somar',      [10, 20, 30]);   // 60.0
calcular('potencia',   [2, 10]);        // 1024.0
calcular('media',      [4, 8, 15, 16]); // 10.75

// Calculadora de Raízes — 2.º grau: x² - 3x + 2 = 0
calcularRaizes([1, -3, 2]);
// grau: 2 | Δ: 1 | raízes: x₁ = 2.0, x₂ = 1.0

// Calculadora de Raízes — 1.º grau: 2x + 6 = 0
calcularRaizes([2, 6]);
// grau: 1 | raiz: x = -3.0
```

---

## 🛠️ Tecnologias

- [Flutter](https://flutter.dev) — framework de UI multiplataforma
- [Dart](https://dart.dev) — linguagem de programação
- Material Design 3 — sistema de design da interface

---

## 📄 Licença

Distribuído sob a licença MIT. Veja `LICENSE` para mais informações.
