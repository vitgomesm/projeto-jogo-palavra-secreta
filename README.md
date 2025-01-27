# Jogo Secreto

## Descrição
O **Jogo Secreto** é um jogo interativo e divertido desenvolvido com HTML, CSS e JavaScript. O objetivo é adivinhar o número secreto gerado aleatoriamente pelo programa, com dicas para ajudar o jogador a chegar na resposta correta.

---

## Funcionalidades
- Geração automática de um número secreto dentro de um intervalo (1 a 10, por padrão).
- Entrada para o jogador inserir um palpite.
- Fornecimento de dicas baseadas no palpite:
  - "O número secreto é maior."
  - "O número secreto é menor."
  - "Você acertou!"
- Opção de reiniciar o jogo após o acerto.
- Feedback por voz usando a biblioteca ResponsiveVoice.

---

## Como jogar
1. Clone ou baixe este repositório em sua máquina.
2. Certifique-se de que o arquivo é composto por:
   - `index.html`: estrutura principal.
   - `style.css`: estilização visual.
   - `app.js`: lógica do jogo.
   - Pasta `img` com as imagens usadas no jogo.
3. Abra o arquivo `index.html` em um navegador.
4. Insira um número no campo de entrada e pressione o botão "Chutar".
5. Siga as dicas até adivinhar o número secreto.

---

## Tecnologias utilizadas
- **HTML5**: Estrutura do jogo.
- **CSS3**: Estilização responsiva e visual moderno.
- **JavaScript**: Lógica interativa.
- **ResponsiveVoice.js**: Feedback de voz.

---

## Estrutura do projeto
```
JogoSecreto/
├── index.html   # Estrutura do jogo
├── style.css    # Estilo e design
├── app.js       # Lógica do jogo
└── img/         # Imagens usadas no projeto
```

---

## Exemplo de código
### Função principal de verificação do palpite:
```javascript
function verificarChute() {
    let chute = document.querySelector('input').value;
    if (chute == numeroSecreto) { 
        exibirTextoNaTela('h1', 'Você acertou!');
        let palavraTentativa = tentativas > 1 ? 'tentativas' : 'tentativa';
        let mensagemTentativas = `Você descobriu o número secreto com ${tentativas} ${palavraTentativa}!`;
        exibirTextoNaTela('p', mensagemTentativas);
        document.getElementById('reiniciar').removeAttribute('disabled');
    } else {
        if (chute > numeroSecreto) {
            exibirTextoNaTela('p', 'O número secreto é menor');
        } else {
            exibirTextoNaTela('p', 'O número secreto é maior');
        }
        tentativas++;
        limparCampo();
    }
}
```

---

## Melhorias futuras
- Permitir escolher diferentes intervalos para o número secreto.
- Adicionar modos de dificuldade (ex.: mais dicas ou limite de tentativas).
- Incluir pontuação e histórico de melhores resultados.
- Melhorar a interface gráfica com animações e sons.

---

## Como contribuir
1. Faça um fork do repositório.
2. Crie uma branch para suas alterações: `git checkout -b minha-branch`.
3. Faça o commit das suas mudanças: `git commit -m 'Descrição das alterações'`.
4. Envie suas mudanças para o repositório remoto: `git push origin minha-branch`.
5. Abra um Pull Request.

---

## Licença
Este projeto é licenciado sob a [MIT License](LICENSE).

---

