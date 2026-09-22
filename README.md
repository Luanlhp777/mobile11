# Mobile 11 — Flutter | AlertDialog e SnackBar

Projeto desenvolvido em aula para estudar diferentes formas de fornecer **feedback ao usuário em aplicações Flutter**, utilizando `AlertDialog` e `SnackBar`.

Durante a aula foi utilizada uma calculadora como aplicação-base para implementar e testar os conceitos apresentados.

---

## 🎯 Objetivo da aula

Compreender e praticar:

- exibição de mensagens com `SnackBar`;
- criação de caixas de diálogo com `AlertDialog`;
- utilização de `ScaffoldMessenger`;
- utilização de `showDialog`;
- interação com botões dentro de um alerta;
- fechamento de diálogos com `Navigator.pop`;
- criação de regras para definir qual feedback apresentar ao usuário.

---

## 🛠️ Tecnologias utilizadas

- Flutter
- Dart
- Material Design
- Git
- GitHub

---

## 📂 Estrutura do repositório

```text
mobile11/
├── 13 - Flutter - Alert e Toast.pdf
├── 14 - Exercício Alert e SnackBar.pdf
├── README.md
└── flutter_appcalculadora_completa/
    └── lib/
        └── main.dart
```

---

# 📱 Aplicação utilizada

Para praticar os conceitos da aula foi utilizada uma calculadora desenvolvida em Flutter.

Ela permite realizar:

- soma;
- subtração;
- multiplicação;
- divisão.

A calculadora funciona como base para aplicar as regras de `AlertDialog` e `SnackBar`.

---

# 📢 SnackBar

O `SnackBar` permite apresentar uma mensagem temporária ao usuário sem interromper o fluxo principal da aplicação.

No projeto foi criada a função:

```dart
void mostrarToast(String mensagem) {
  ScaffoldMessenger.of(context).showSnackBar(
    SnackBar(
      content: Text(mensagem),
      duration: const Duration(seconds: 3),
    ),
  );
}
```

Quando uma operação é realizada normalmente, a aplicação apresenta:

```text
OPERAÇÃO REALIZADA
```

---

# ⚠️ AlertDialog

O `AlertDialog` é utilizado quando a aplicação precisa chamar a atenção do usuário e solicitar uma interação.

No exercício foi criado um alerta com duas opções:

```text
SIM
NÃO
```

Estrutura utilizada:

```dart
AlertDialog(
  title: const Text("Atenção"),
  content: Text(mensagem),
  actions: [
    TextButton(
      onPressed: () {
        Navigator.pop(context);
      },
      child: const Text("SIM"),
    ),
    TextButton(
      onPressed: () {
        Navigator.pop(context);
      },
      child: const Text("NÃO"),
    ),
  ],
);
```

O diálogo é fechado utilizando:

```dart
Navigator.pop(context);
```

---

# 🧪 Exercício proposto

O exercício consistiu em implementar uma regra para escolher automaticamente entre `AlertDialog` e `SnackBar` de acordo com o resultado da operação.

Foi criada a função:

```dart
void verificarResultado() {
  if (resultado < 0) {
    mostrarAlerta(
      "ATENÇÃO! RESULTADO MENOR QUE ZERO! DESEJA CONTINUAR?"
    );
  } else {
    mostrarToast("OPERAÇÃO REALIZADA");
  }
}
```

Após realizar uma operação matemática, a aplicação executa:

```dart
verificarResultado();
```

---

## 🔄 Fluxo implementado

```text
Usuário informa os números
        ↓
Escolhe uma operação
        ↓
Aplicação realiza o cálculo
        ↓
verificarResultado()
        ↓
   Resultado < 0 ?
      ↙       ↘
    SIM       NÃO
     ↓         ↓
AlertDialog  SnackBar
     ↓         ↓
SIM / NÃO   Operação
            realizada
```

---

## AlertDialog x SnackBar

| Recurso | Utilização no exercício |
|---|---|
| `SnackBar` | Informa que a operação foi realizada |
| `AlertDialog` | Alerta quando o resultado é menor que zero |
| `ScaffoldMessenger` | Responsável pela exibição do `SnackBar` |
| `showDialog` | Responsável por abrir o diálogo |
| `Navigator.pop` | Fecha o `AlertDialog` |

---

## 🧠 Conceitos praticados

- Flutter
- Dart
- `StatefulWidget`
- `setState`
- `TextEditingController`
- `ScaffoldMessenger`
- `SnackBar`
- `showDialog`
- `AlertDialog`
- `TextButton`
- `Navigator.pop`
- estruturas condicionais
- funções
- interação com o usuário
- feedback visual

---

## ▶️ Como executar

Entre na pasta do projeto:

```bash
cd flutter_appcalculadora_completa
```

Instale as dependências:

```bash
flutter pub get
```

Execute:

```bash
flutter run
```

---

## ✅ Status

**Exercício concluído.**

A aplicação implementa os dois mecanismos estudados na aula:

```text
Resultado negativo → AlertDialog
Demais resultados → SnackBar
```

---

## 👨‍💻 Autor

**Luan Araujo**

Projeto acadêmico desenvolvido para prática de **Desenvolvimento Mobile com Flutter e Dart**.
