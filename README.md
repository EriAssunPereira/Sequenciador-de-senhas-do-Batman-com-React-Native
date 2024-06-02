# Sequenciador-de-senhas-do-Batman-com-React-Native

# Desenvolvendo um Sequenciador de Senhas do Batman com React Native

Neste artigo, vamos mergulhar na criação de um aplicativo React Native que simula um sequenciador de senhas inspirado no universo do Batman. Nosso objetivo é desenvolver uma ferramenta intuitiva e funcional que permita aos usuários gerar senhas personalizadas com a estética característica do Cavaleiro das Trevas.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte instalado em seu ambiente de desenvolvimento:

1. **Node.js e npm**: O React Native requer o Node.js e o npm para funcionar. Você pode baixá-los em [nodejs.org](https://nodejs.org/).

2. **Expo CLI**: O Expo é uma plataforma que facilita o desenvolvimento de aplicativos React Native. Instale o Expo CLI globalmente com o seguinte comando:

    ```bash
    npm install -g expo-cli
    ```

3. **Editor de código**: Use o editor de código de sua preferência (por exemplo, Visual Studio Code).

## Criando o Projeto

Vamos criar um novo projeto React Native usando o Expo. Abra o terminal e execute os seguintes comandos:

```bash
expo init BatmanPasswordSequencer
cd BatmanPasswordSequencer
```

Escolha o template "blank" quando solicitado.

## Estrutura do Projeto

Nosso projeto terá a seguinte estrutura:

```
BatmanPasswordSequencer/
├── App.js
├── assets/
│   └── batman-logo.png
├── components/
│   ├── PasswordGenerator.js
│   └── PasswordList.js
└── ...
```

- `App.js`: O ponto de entrada do aplicativo.
- `assets/`: Pasta para armazenar recursos, como imagens.
- `components/`: Pasta para componentes reutilizáveis.

## Implementando o Sequenciador de Senhas

### 1. Tela Inicial

Vamos começar criando a tela inicial do aplicativo. Ela exibirá o logotipo do Batman e um botão para gerar senhas.

```jsx
// components/PasswordGenerator.js

import React from 'react';
import { View, Text, Image, TouchableOpacity } from 'react-native';
import { styles } from './styles';

const PasswordGenerator = () => {
  return (
    <View style={styles.container}>
      <Image source={require('../assets/batman-logo.png')} style={styles.logo} />
      <TouchableOpacity style={styles.button}>
        <Text style={styles.buttonText}>Gerar Senha</Text>
      </TouchableOpacity>
    </View>
  );
};

export default PasswordGenerator;
```

### 2. Lista de Senhas

Agora, vamos criar a lista de senhas geradas. Ela será exibida após o usuário clicar no botão "Gerar Senha".

```jsx
// components/PasswordList.js

import React, { useState } from 'react';
import { View, Text, FlatList } from 'react-native';
import { styles } from './styles';

const PasswordList = () => {
  const [passwords, setPasswords] = useState([]);

  // Lógica para gerar senhas aqui

  return (
    <View style={styles.container}>
      <FlatList
        data={passwords}
        renderItem={({ item }) => (
          <Text style={styles.password}>{item}</Text>
        )}
        keyExtractor={(item) => item}
      />
    </View>
  );
};

export default PasswordList;
```

### 3. Estilização

Por fim, estilize os componentes conforme sua preferência. Crie um arquivo `styles.js` para centralizar os estilos.

```jsx
// components/styles.js

import { StyleSheet } from 'react-native';

export const styles = StyleSheet.create({
  container: {
    flex: 1,
    alignItems: 'center',
    justifyContent: 'center',
  },
  logo: {
    width: 150,
    height: 150,
    marginBottom: 20,
  },
  button: {
    backgroundColor: '#333',
    padding: 10,
    borderRadius: 5,
  },
  buttonText: {
    color: '#fff',
    fontSize: 16,
  },
  password: {
    fontSize: 18,
    marginVertical: 5,
  },
});
```

## Conclusão

Com esses módulos, qualquer um estará está pronto para criar seu sequenciador de senhas do Batman! Lembre-se de adicionar a lógica para gerar senhas aleatórias e personalizadas. Divirta-se desenvolvendo e que a força esteja com cada um de vocês.
