# poderada-farol


### Vídeo do projeto concluido:

https://youtube.com/shorts/gyT1P4GEISQ?feature=share


### Código Utilizado:

```
// Variável para guardar o tempo da última troca
unsigned long tempoAnterior = 0;

// Variável que indica em qual parte do ciclo o farol está
int etapa = 0;

// Ponteiro que aponta para a variável 'etapa'
int *ptrEtapa = &etapa;

void setup() {
  // Define os pinos dos LEDs como saídas
  pinMode(12, OUTPUT); // LED vermelho
  pinMode(8, OUTPUT);  // LED amarelo
  pinMode(10, OUTPUT); // LED azul

  // Inicia a comunicação com o monitor serial
  Serial.begin(9600);
}

void loop() {
  // Pega o tempo atual desde que o Arduino foi ligado
  unsigned long tempoAtual = millis();

  // Mostra o valor atual da etapa pelo ponteiro
  Serial.print("Etapa atual (via ponteiro): ");
  Serial.println(*ptrEtapa); // Usa o * para acessar o valor de 'etapa'

  // Escolhe o que fazer dependendo da etapa do ciclo
  switch (*ptrEtapa) {  // Usa o valor apontado pelo ponteiro

    case 0: // Etapa 0: LED vermelho por 6 segundos
      digitalWrite(12, HIGH);
      if (tempoAtual - tempoAnterior >= 6000) {
        digitalWrite(12, LOW);
        *ptrEtapa = 1;           // Altera a etapa via ponteiro
        tempoAnterior = tempoAtual;
      }
      break;

    case 1: // Etapa 1: LED amarelo por 4 segundos
      digitalWrite(8, HIGH);
      if (tempoAtual - tempoAnterior >= 4000) {
        digitalWrite(8, LOW);
        *ptrEtapa = 2;           // Altera via ponteiro
        tempoAnterior = tempoAtual;
      }
      break;

    case 2: // Etapa 2: LED azul por 2 segundos
      digitalWrite(10, HIGH);
      if (tempoAtual - tempoAnterior >= 2000) {
        digitalWrite(10, LOW);
        *ptrEtapa = 0;           // Reinicia o ciclo via ponteiro
        tempoAnterior = tempoAtual;
      }
      break;
  }

  delay(200); // Pequena pausa só para evitar prints excessivos no Serial Monitor
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
| Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores | Até 3 | Até 1,5 | 0   | Cores corretas com fios devidamente conectados, 3
| Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo | Até 3 | Até 1,5 | 0  | O tempo está correto em cada led, 3
| Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) | Até 3 | Até 1,5 | 0 | Código foi comentado, 3
| Ir além: Implementou um componente de extra, fez com millis() ao invés do delay() e/ou usou ponteiros no código | Até 1 | Até 0,5 | 0 | Usou milles, 1
| **Pontuação Total** | Total: 10 pontos |  |  |  |



### Tabela de Avaliação entre Pares

**Avaliador:** Thúlio Bacco 

| Critério | Contempla (Pontos) | Contempla Parcialmente (Pontos) | Não Contempla (Pontos) | Observações do Avaliador |
|-----------|--------------------|----------------------------------|------------------------|---------------------------|
| Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores | Até 3 | Até 1,5 | 0   | Tudo perfeito, 3
| Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo | Até 3 | Até 1,5 | 0  | Tempo batento com o necessário, 3
| Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) | Até 3 | Até 1,5 | 0 | Código bem comentado, 3
| Ir além: Implementou um componente de extra, fez com millis() ao invés do delay() e/ou usou ponteiros no código | Até 1 | Até 0,5 | 0 | Usou milles, 1
| **Pontuação Total** | Total: 10 pontos |  |  |  |

