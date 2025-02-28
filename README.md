//ROSILAINE

// Função que gera um número aleatório entre 1 e 10
function gerarNumeroAleatorio() {
    return Math.floor(Math.random() * 10) + 1;
}

// Função principal do jogo
function adivinharNumero() {
    // Gerar um número aleatório
    const numeroCorreto = gerarNumeroAleatorio();
    let tentativas = 0;
    let numeroUsuario;

    // Loop para continuar pedindo ao usuário até acertar
    do {
        // Solicita o número ao usuário
        numeroUsuario = parseInt(prompt("Adivinhe o número entre 1 e 10:"));

        // Verifica se a entrada é válida
        if (isNaN(numeroUsuario) || numeroUsuario < 1 || numeroUsuario > 10) {
            alert("Por favor, insira um número entre 1 e 10.");
            continue;
        }

        // Aumenta o contador de tentativas
        tentativas++;

        // Compara o número do usuário com o número correto
        if (numeroUsuario < numeroCorreto) {
            alert("O número que você inseriu é menor que o correto.");
        } else if (numeroUsuario > numeroCorreto) {
            alert("O número que você inseriu é maior que o correto.");
        } else {
            alert(`Parabéns! Você acertou o número ${numeroCorreto} em ${tentativas} tentativas.`);
        }
    } while (numeroUsuario !== numeroCorreto); // Continua até acertar o número
}

// Chama a função para começar o jogo
adivinharNumero();

