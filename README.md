## Organização das pastas: 
components/: Para armazenar componentes reutilizáveis (ainda vamos criar).
screens/: Contém as telas principais do aplicativo.
navigation/: Centraliza a configuração da navegação entre as telas.


## Organização das telas:


**App.tsx (navegação no projet):**

***Importações:***
React é importado para permitir o uso de JSX.
<kbd>NavigationContainer</kbd> é importado de @react-navigation/native para fornecer um contexto de navegação para o aplicativo.
<kbd>NativeBaseProvider</kbd> é importado de native-base para fornecer o contexto necessário para os componentes do Native Base.
<kbd>AppNavigator</kbd> é importado de ./src/navigation/AppNavigator para gerenciar as rotas e navegação entre as telas do aplicativo.

***Definição do Componente App:***
<kbd>NativeBaseProvider:</kbd> Envolve o aplicativo, fornecendo o contexto necessário para que os componentes do Native Base funcionem corretamente e utilizando o tema definido.
<kbd>NavigationContainer:</kbd> Envolve o AppNavigator, fornecendo o contexto de navegação necessário para que o stack navigator funcione corretamente.
<kbd>AppNavigator /:</kbd> Renderiza o componente AppNavigator, que define as rotas e a navegação entre as diferentes telas do aplicativo.

***Exportação do Componente App:***
Exporta o componente App como padrão para que possa ser utilizado como ponto de entrada do aplicativo.


**/AppNavigator.tsx (gerenciar a navegação entre as telas):**

***Definição do Tipo RootStackParamList:***
Define os tipos de parâmetros esperados para cada tela no navegador. 
Neste caso, como não há parâmetros esperados em nenhuma das telas, todos os valores são undefined.

***Criação do Stack Navigator:***
Cria uma instância do stack navigator com base no tipo RootStackParamList. 
Isso define o tipo de navegação para garantir a segurança dos tipos em todo o aplicativo.

***Definição do Componente AppNavigator:***
Define o componente AppNavigator que renderiza o stack navigator.
O Stack.Navigator configura as rotas do aplicativo e define a tela inicial (initialRouteName) como "Welcome". 
Cada Stack.Screen configura uma rota, associando um nome à tela correspondente.

***Exportação do AppNavigator:***
Exporta o componente AppNavigator para que possa ser usado em outros lugares, como o arquivo App.tsx.


**/WelcomeScreen.tsx (componentes simples do Native Base):**

***Tipo WelcomeScreenNavigationProp:***
Define o tipo de navegação para a tela de boas-vindas. Usa NativeStackNavigationProp com RootStackParamList e a rota 'Welcome'. 

***Tipo Props:***
Define as propriedades que o componente WelcomeScreen aceita, especificamente o objeto de navegação.

***Componente WelcomeScreen:***
<kbd>NativeBaseProvider:</kbd> Envolve o conteúdo, fornecendo o contexto do Native Base.
<kbd>Center:</kbd> Centraliza seu conteúdo horizontal e verticalmente, e usa um fundo branco.
<kbd>Box:</kbd> Um contêiner que pode ser usado para estilizar e organizar o layout.
<kbd>Button:</kbd> Um botão que, ao ser pressionado, navega para a tela de Login usando navigation.navigate('Login').


**/LoginScreen.tsx:**

***Tipo LoginScreenNavigationProp:***
Define o tipo de navegação para a tela de login. Usa NativeStackNavigationProp com RootStackParamList e a rota 'Login'.

***Componente LoginScreen:***
<kbd>NativeBaseProvider:</kbd> Envolve o conteúdo, fornecendo o contexto do Native Base.
<kbd>Centerr:</kbd> Centraliza seu conteúdo horizontal e verticalmente, com fundo branco.
<kbd>Box:</kbd> Um contêiner que organiza os elementos dentro da tela.
<kbd>Input:</kbd> Campos de entrada para o e-mail e senha. O campo de senha tem a propriedade secureTextEntry para ocultar o texto.
<kbd>Buttonn:</kbd> Dois botões:
        O primeiro botão navega para a tela de listagem de consultas ao ser pressionado.
        O segundo botão navega para a tela de cadastro.


**/SignUpScreen.tsx:**

***Tipo SignUpScreenNavigationProp:***
Define o tipo de navegação para a tela de cadastro. Usa NativeStackNavigationProp com RootStackParamList e a rota 'SignUp'.

***Componente SignUpScreen:***
<kbd>NativeBaseProvider:</kbd> Envolve o conteúdo, fornecendo o contexto do Native Base.
<kbd>Center:</kbd> Centraliza seu conteúdo horizontal e verticalmente, com fundo branco.
<kbd>Box:</kbd> Um contêiner que organiza os elementos dentro da tela.
<kbd>Input:</kbd> Campos de entrada para nome, e-mail e senha. O campo de senha tem a propriedade secureTextEntry para ocultar o texto.
<kbd>Buttonn:</kbd> Um botão:
    Navega para a tela de login quando pressionado.


**/ConsultationsListScreen.tsx:**

***Tipo ConsultationsListScreenNavigationProp:***
Define o tipo de navegação para a tela de listagem de consultas. Usa NativeStackNavigationProp com RootStackParamList e a rota 'ConsultationsList'

***Dados Mockados mockConsultations:***
Array de objetos representando consultas simuladas, cada uma com um id, nome do doctor, date e status.

***Componente ConsultationsListScreen:***
<kbd>NativeBaseProvider:</kbd> Envolve o conteúdo, fornecendo o contexto do Native Base.
<kbd>Center:</kbd> Centraliza seu conteúdo horizontal e verticalmente, com fundo branco.
<kbd>Box:</kbd> Um contêiner que organiza os elementos dentro da tela.
<kbd>FlatList:</kbd> Componente para exibir uma lista de itens roláveis:
<kbd>data:</kbd> Fonte de dados para a lista, usando mockConsultations.
renderItem: Função para renderizar cada item da lista:
<kbd>Box:</kbd> Contêiner para cada item, com borda inferior, margem e preenchimento.
<kbd>Text:</kbd> Exibe detalhes da consulta como o nome do médico, data e status.
<kbd>Buttonn:</kbd> Um botão que navega para a tela de agendamento de consultas quando pressionado.
<kbd>keyExtractor:</kbd> Função para extrair uma chave única para cada item da lista usando o id.


**/ScheduleConsultationScreen.tsx:**

***Tipo ScheduleConsultationScreenNavigationProp:***
Define o tipo de navegação para a tela de agendamento de consultas, usando NativeStackNavigationProp com RootStackParamList e a rota 'ScheduleConsultation'.

***Tipo Props:***
Define as propriedades que o componente ScheduleConsultationScreen aceita, especificamente o objeto de navegação.

***Componente ScheduleConsultationScreen:***
<kbd>NativeBaseProvider:</kbd> Envolve o conteúdo, fornecendo o contexto do Native Base.
<kbd>Center:</kbd> Centraliza o conteúdo horizontal e verticalmente, com fundo branco.
<kbd>Box:</kbd> Um contêiner para organizar os elementos dentro da tela.
<kbd>Select:</kbd> Componente para selecionar um item de uma lista:
<kbd>placeholder:</kbd> Texto exibido quando nenhum item está selecionado.
<kbd>Select.Item:</kbd> Itens que podem ser selecionados, cada um com um label e um value.
<kbd>Input:</kbd> Campo de entrada para o usuário inserir a data da consulta.
<kbd>Buttonn:</kbd> Botão que navega para a tela de confirmação de agendamento quando pressionado, com o texto "Agendar".


**/ConfirmAppointmentScreen.tsx:**

***Tipo ConfirmAppointmentScreenNavigationProp:***
Define o tipo de navegação para a tela de confirmação de agendamento, usando NativeStackNavigationProp com RootStackParamList e a rota 'ConfirmAppointment'.

***Componente ConfirmAppointmentScreen:***
<kbd>NativeBaseProvider:</kbd> Envolve o conteúdo, fornecendo o contexto do Native Base.
<kbd>Centerr:</kbd> Centraliza o conteúdo horizontal e verticalmente, com fundo branco.
<kbd>Box:</kbd> Um contêiner para organizar os elementos dentro da tela.
<kbd>Text:</kbd>Exibe a mensagem "Consulta agendada com sucesso!".
<kbd>Buttonn:</kbd> Botão que navega de volta para a tela de listagem de consultas quando pressionado, com o texto "Voltar para Consultas". 
    O espaçamento superior (mt={4}) é adicionado para separar o botão do texto. 