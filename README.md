# Formulário de Cadastro com Validação e API ViaCEP

Este projeto consiste em um formulário de cadastro HTML que realiza validações de campos (nome, idade, CPF e CEP) e utiliza a API ViaCEP para preencher automaticamente os campos de endereço (logradouro, bairro, cidade e estado) com base no CEP informado.

## Funcionalidades

1. **Validação de Campos**:
   - **Nome**: Campo obrigatório.
   - **Idade**: Deve ser um número válido.
   - **CPF**: Validação de CPF usando algoritmo de verificação.
   - **CEP**: Deve conter 8 dígitos numéricos.

2. **Integração com API ViaCEP**:
   - Ao informar um CEP válido, o sistema consulta a API ViaCEP e preenche automaticamente os campos de endereço (logradouro, bairro, cidade e estado).

3. **Campos de Endereço Somente Leitura**:
   - Os campos de endereço são preenchidos automaticamente e não podem ser editados manualmente.

4. **Validação no Envio**:
   - O formulário só é enviado se todos os campos estiverem válidos.

---

## Como Funciona

### Validação de CPF
O CPF é validado usando um algoritmo que verifica os dígitos verificadores. O código remove caracteres não numéricos e valida se o CPF possui 11 dígitos.

### Integração com ViaCEP
Ao informar um CEP e sair do campo (evento `blur`), o sistema faz uma requisição à API ViaCEP. Se o CEP for válido, os campos de endereço são preenchidos automaticamente.

### Validação no Envio
Antes de enviar o formulário, o sistema valida:
- Se o nome foi preenchido.
- Se a idade é um número válido.
- Se o CPF é válido.
- Se o CEP é válido e possui 8 dígitos.

---

## Estrutura do Código

### HTML
- O formulário contém campos para:
  - Nome
  - Idade
  - CPF
  - CEP
  - Logradouro (preenchido automaticamente)
  - Bairro (preenchido automaticamente)
  - Cidade (preenchido automaticamente)
  - Estado (preenchido automaticamente)

### JavaScript
- **Validação de CPF**: Função `validarCPF(cpf)`.
- **Consulta de CEP**: Função `buscarEndereco(cep)` que usa a API ViaCEP.
- **Validação do Formulário**: Função `validarFormulario()` que verifica todos os campos antes do envio.
- **Evento `blur` no CEP**: Quando o usuário sai do campo de CEP, o sistema consulta a API ViaCEP.

### Dependências
- **jQuery**: Utilizado para simplificar a manipulação do DOM e requisições AJAX.

---

## Como Usar

1. Clone o repositório ou baixe o arquivo `index.html`.
2. Abra o arquivo `index.html` em um navegador.
3. Preencha os campos do formulário:
   - **Nome**: Insira seu nome.
   - **Idade**: Insira sua idade (apenas números).
   - **CPF**: Insira um CPF válido.
   - **CEP**: Insira um CEP válido (8 dígitos).
4. Ao sair do campo de CEP, os campos de endereço serão preenchidos automaticamente.
5. Clique em **Enviar** para submeter o formulário (se todos os campos estiverem válidos).

---

## Melhorias Futuras

1. **Validação de CEP com Hífen**:
   - Atualmente, o CEP deve ser inserido sem hífen. Uma melhoria seria aceitar CEPs com hífen (ex: `12345-678`).

2. **Máscara de Campos**:
   - Adicionar máscaras para CPF e CEP para melhorar a experiência do usuário.

3. **Validação de Idade**:
   - Adicionar validação para garantir que a idade seja um número positivo e dentro de um intervalo razoável.

4. **Feedback Visual**:
   - Adicionar mensagens de erro ou sucesso diretamente no formulário, em vez de usar `alert()`.

---

## Tecnologias Utilizadas

- **HTML**: Estrutura do formulário.
- **JavaScript**: Validações e integração com a API ViaCEP.
- **jQuery**: Facilita a manipulação do DOM e requisições AJAX.
- **API ViaCEP**: Consulta de endereço a partir do CEP.

---

## Como Contribuir

1. Faça um **fork** deste repositório.
2. Crie uma **branch** para sua feature (`git checkout -b feature/nova-feature`).
3. Faça commit das suas alterações (`git commit -m 'Adicionando nova feature'`).
4. Faça push para a branch (`git push origin feature/nova-feature`).
5. Abra um **Pull Request** para revisão.

---

## Licença

Este projeto está licenciado sob a licença MIT. Consulte o arquivo [LICENSE](LICENSE) para mais detalhes.

---

## Contato

- **Nome**: [Seu Nome]
- **E-mail**: [Seu E-mail]
- **GitHub**: [Link do seu GitHub]
