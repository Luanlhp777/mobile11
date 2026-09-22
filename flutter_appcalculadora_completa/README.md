# Calculadora Flutter — AlertDialog e SnackBar

Aplicação desenvolvida em **Flutter e Dart** e utilizada como base prática para o estudo de **feedback ao usuário com `AlertDialog` e `SnackBar`**.

A calculadora realiza operações matemáticas básicas e aplica diferentes formas de feedback de acordo com o resultado obtido.

---

## 🎯 Objetivo

Utilizar uma aplicação funcional para praticar:

- `SnackBar` para mensagens temporárias;
- `AlertDialog` para alertas que exigem interação;
- `ScaffoldMessenger`;
- `showDialog`;
- `Navigator.pop`;
- estruturas condicionais;
- gerenciamento de estado com `setState`.

---

## 🧮 Funcionalidades

A calculadora permite realizar:

- Soma
- Subtração
- Multiplicação
- Divisão

Os valores são informados através de campos `TextField` e processados utilizando `TextEditingController`.

---

## ⚠️ Validação do resultado

Após cada operação, a função `verificarResultado()` analisa o valor calculado:

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

O comportamento da aplicação é:

```text
Resultado da operação
        │
        ▼
verificarResultado()
        │
        ▼
 Resultado < 0?
    ┌───────┴───────┐
   SIM             NÃO
    │                │
    ▼                ▼
AlertDialog       SnackBar
    │                │
 SIM / NÃO     OPERAÇÃO REALIZADA
```

---

## 📢 SnackBar

Quando o resultado não é negativo, uma mensagem temporária confirma a operação:

```text
OPERAÇÃO REALIZADA
```

A mensagem é exibida através de:

```dart
ScaffoldMessenger.of(context).showSnackBar(...)
```

---

## 🚨 AlertDialog

Quando o resultado é menor que zero, a aplicação apresenta:

```text
ATENÇÃO!
RESULTADO MENOR QUE ZERO!
DESEJA CONTINUAR?
```

O usuário pode escolher:

```text
SIM
NÃO
```

O diálogo é fechado utilizando:

```dart
Navigator.pop(context);
```

---

## 🛠️ Tecnologias

- Flutter
- Dart
- Material Design

---

## ▶️ Executando o projeto

Instale as dependências:

```bash
flutter pub get
```

Execute a aplicação:

```bash
flutter run
```

---

## 📚 Conceitos praticados

`StatefulWidget` • `setState` • `TextField` • `TextEditingController` • `SnackBar` • `ScaffoldMessenger` • `AlertDialog` • `showDialog` • `Navigator` • Estruturas condicionais

---

## 📌 Contexto

Este aplicativo faz parte do repositório **Mobile 11**, desenvolvido durante as aulas de Desenvolvimento Mobile.

A calculadora foi utilizada como aplicação-base para o exercício de implementação e comparação entre **AlertDialog e SnackBar**.

---

## 👨‍💻 Autor

**Luan Araujo**

Projeto acadêmico desenvolvido para prática de **Desenvolvimento Mobile com Flutter e Dart**.
