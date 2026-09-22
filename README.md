# Mobile 11 — Flutter | AlertDialog e SnackBar

Projeto desenvolvido em aula para praticar **mensagens de feedback ao usuário em Flutter**, utilizando `SnackBar` e `AlertDialog`.

Como exercício prático, foi desenvolvida uma calculadora capaz de realizar as quatro operações matemáticas básicas.

---

## Objetivo da aula

Praticar conceitos como:

- criação de interfaces com Flutter;
- utilização de `StatefulWidget`;
- gerenciamento de estado com `setState`;
- captura de dados com `TextField`;
- uso de `TextEditingController`;
- conversão de valores com `double.tryParse`;
- operações matemáticas;
- exibição de mensagens com `SnackBar`;
- criação de janelas modais com `AlertDialog`;
- navegação com `Navigator.pop`.

---

## Tecnologias utilizadas

- Flutter
- Dart
- Material Design
- Git
- GitHub

---

## Estrutura do projeto

```text
mobile11/
├── 13 - Flutter - Alert e Toast.pdf
├── 14 - Exercício Alert e SnackBar.pdf
└── flutter_appcalculadora_completa/
    └── lib/
        └── main.dart
```

---

## Funcionalidades

A aplicação permite informar dois números e realizar as seguintes operações:

- soma;
- subtração;
- multiplicação;
- divisão.

O resultado também é exibido diretamente na interface.

---

## Entrada de dados

Os valores são capturados utilizando dois `TextField` controlados por:

```dart
TextEditingController
```

Exemplo:

```dart
final TextEditingController numero1Controller = TextEditingController();
final TextEditingController numero2Controller = TextEditingController();
```

Os textos digitados são convertidos para `double`:

```dart
double n1 = double.tryParse(numero1Controller.text) ?? 0;
double n2 = double.tryParse(numero2Controller.text) ?? 0;
```

Caso o valor informado não seja válido, é utilizado `0`.

---

## Gerenciamento de estado

O resultado da operação é armazenado na variável:

```dart
double resultado = 0;
```

Sempre que uma operação é realizada, o valor é atualizado com:

```dart
setState(() {
  resultado = n1 + n2;
});
```

O `setState()` faz com que a interface seja reconstruída com o novo resultado.

---

## SnackBar

Na operação de soma, o aplicativo apresenta uma mensagem utilizando `SnackBar`.

```dart
ScaffoldMessenger.of(context).showSnackBar(
  SnackBar(
    content: Text(mensagem),
    duration: const Duration(seconds: 3),
  ),
);
```

O `SnackBar` é utilizado para exibir uma mensagem temporária na tela sem interromper totalmente a interação do usuário.

Exemplo utilizado:

```dart
mostrarToast("Resultado: $resultado");
```

---

## AlertDialog

Na operação de subtração, o resultado é apresentado através de um `AlertDialog`.

```dart
showDialog(
  context: context,
  builder: (context) {
    return AlertDialog(
      title: const Text("Resultado"),
      content: Text(mensagem),
      actions: [
        TextButton(
          onPressed: () {
            Navigator.pop(context);
          },
          child: const Text("Ok"),
        ),
      ],
    );
  },
);
```

O `AlertDialog` cria uma janela modal que exige uma interação do usuário para ser fechada.

---

## SnackBar x AlertDialog

| Recurso | Comportamento |
|---|---|
| `SnackBar` | Exibe uma mensagem temporária na parte inferior da tela |
| `AlertDialog` | Exibe uma janela modal sobre a interface |
| `SnackBar` | Não interrompe completamente a interação |
| `AlertDialog` | Requer uma ação do usuário para fechar |

---

## Operações implementadas

### Soma

```dart
resultado = n1 + n2;
```

Após a operação, o resultado também é mostrado através de um `SnackBar`.

### Subtração

```dart
resultado = n1 - n2;
```

Após a operação, é exibido um `AlertDialog`.

### Multiplicação

```dart
resultado = n1 * n2;
```

### Divisão

```dart
if (n2 == 0) {
  resultado = double.nan;
} else {
  resultado = n1 / n2;
}
```

Também foi incluído tratamento para evitar uma divisão normal por zero.

---

## Interface

Os botões foram organizados em duas linhas utilizando `Row`.

Primeira linha:

```text
Somar | Subtrair
```

Segunda linha:

```text
Multiplicar | Dividir
```

Cada operação utiliza `ElevatedButton.icon`, adicionando um ícone ao botão.

---

## Fluxo da aplicação

```text
Usuário informa os números
        ↓
TextEditingController
        ↓
double.tryParse()
        ↓
Operação matemática
        ↓
setState()
        ↓
Atualização do resultado
        ↓
SnackBar / AlertDialog
```

---

## Como executar

Entre na pasta do projeto:

```bash
cd flutter_appcalculadora_completa
```

Baixe as dependências:

```bash
flutter pub get
```

Execute o aplicativo:

```bash
flutter run
```

---

## Conceitos praticados

- Flutter
- Dart
- StatefulWidget
- State
- setState
- TextField
- TextEditingController
- double.tryParse
- ElevatedButton
- Row
- ScaffoldMessenger
- SnackBar
- showDialog
- AlertDialog
- Navigator
- tratamento de divisão por zero

---

## Status

✅ Atividade desenvolvida em aula para estudo de **AlertDialog, SnackBar e manipulação de estado no Flutter**.

---

## Autor

**Luan Araujo**

Projeto acadêmico desenvolvido para prática de **Desenvolvimento Mobile com Flutter e Dart**.
