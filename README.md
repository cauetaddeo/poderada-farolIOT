# poderada-farol


### Vídeo do projeto concluido:

https://youtube.com/shorts/qnlXVADWeZc?feature=share  


### Código Utilizado:

```
// Variável para guardar o tempo da última troca
unsigned long tempoAnterior = 0;

// Variável que indica em qual parte do ciclo o farol está
int etapa = 0;

void setup() {
  // Define os pinos dos LEDs como saídas
  pinMode(12, OUTPUT); // LED vermelho
  pinMode(8, OUTPUT);  // LED amarelo
  pinMode(10, OUTPUT); // LED azul
  Serial.begin(9600);
}

void loop() {
  // Pega o tempo atual desde que o Arduino foi ligado 
  unsigned long tempoAtual = millis();

  // Escolhe o que fazer dependendo da etapa do ciclo
  switch (etapa) {

    case 0: // Etapa 0: acende o LED vermelho por 6 segundos
      digitalWrite(12, HIGH); // Liga o LED vermelho
      if (tempoAtual - tempoAnterior >= 6000) { 
        digitalWrite(12, LOW); // Desliga o LED vermelho
        etapa = 1;             // Passa para a próxima etapa
        tempoAnterior = tempoAtual; // Atualiza o tempo de referência
      }
      break;

    case 1: // Etapa 1: acende o LED amarelo por 4 segundos
      digitalWrite(8, HIGH); // Liga o LED amarelo
      if (tempoAtual - tempoAnterior >= 4000) {
        digitalWrite(8, LOW); // Desliga o LED amarelo
        etapa = 2;            // Passa para a próxima etapa
        tempoAnterior = tempoAtual; // Atualiza o tempo
      }
      break;

    case 2: // Etapa 2: acende o LED azul por 2 segundos
      digitalWrite(10, HIGH); // Liga o LED azul
      if (tempoAtual - tempoAnterior >= 2000) {
        digitalWrite(10, LOW); // Desliga o LED azul
        etapa = 0;             // Volta para a primeira etapa (reinicia o ciclo)
        tempoAnterior = tempoAtual; // Atualiza o tempo
      }
      break;
  }
}


```


### Tabela dos componentes utilizados:

| **Componente**                      | **Quantidade** | **Descrição / Função**                                                                 |
|------------------------------------|----------------|-----------------------------------------------------------------------------------------|
| LED Vermelho                       | 1              | Indica o sinal de **pare** no farol.                                                   |
| LED Amarelo                        | 1              | Indica o sinal de **atenção** (transição entre verde e vermelho).                      |
| LED Azul                           | 1              | Representa o sinal de **siga** (ou personalizado conforme o projeto IoT).              |
| Arduino Uno                        | 1              | Microcontrolador responsável por controlar os LEDs e a lógica do farol.                |
| Resistores                         | 3              | Limitam a corrente dos LEDs, evitando que queimem.                                     |
| Jumpers (macho-macho / macho-fêmea)| 11             | Realizam as conexões entre o Arduino, os resistores e os LEDs.                         |
| Estrutura de madeira (suporte)     | 1              | Suporte físico no formato de farol, onde os LEDs foram encaixados.                     |




### Algumas fotos da montagem:


1.1:
![Imagem do WhatsApp de 2025-10-28 à(s) 14 22 44_603857ea](https://github.com/user-attachments/assets/39ce2942-8d6b-420d-b5ed-b0e828f6625e)

1.2:
![Imagem do WhatsApp de 2025-10-28 à(s) 14 22 44_dada1f46](https://github.com/user-attachments/assets/9b220086-080d-40b5-9718-477ab54832cb)

1.3:
![Imagem do WhatsApp de 2025-10-28 à(s) 14 22 44_fa2ce59f](https://github.com/user-attachments/assets/2200a93c-f7aa-486f-bb51-10b26f9383d6)




### Tabela de Avaliação entre Pares

**Avaliador:** António Di Cilio

| Critério | Contempla (Pontos) | Contempla Parcialmente (Pontos) | Não Contempla (Pontos) | Observações do Avaliador |
|-----------|--------------------|----------------------------------|------------------------|---------------------------|
| Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores | Até 3 | Até 1,5 | 0   | Cores corretas com fios devidamente conectados
| Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo | Até 3 | Até 1,5 | 0  | O tempo está correto em cada led
| Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) | Até 3 | Até 1,5 | 0 | Código foi comentado 
| Ir além: Implementou um componente de extra, fez com millis() ao invés do delay() e/ou usou ponteiros no código | Até 1 | Até 0,5 | 0 | Usou milles
| **Pontuação Total** | Total: 10 pontos |  |  |  |



### Tabela de Avaliação entre Pares

**Avaliador:** Thúlio Bacco 

| Critério | Contempla (Pontos) | Contempla Parcialmente (Pontos) | Não Contempla (Pontos) | Observações do Avaliador |
|-----------|--------------------|----------------------------------|------------------------|---------------------------|
| Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores | Até 3 | Até 1,5 | 0   | Tudo perfeito
| Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo | Até 3 | Até 1,5 | 0  | Tempo batento com o necessário
| Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) | Até 3 | Até 1,5 | 0 | Código bem comentado 
| Ir além: Implementou um componente de extra, fez com millis() ao invés do delay() e/ou usou ponteiros no código | Até 1 | Até 0,5 | 0 | Usou milles
| **Pontuação Total** | Total: 10 pontos |  |  |  |

