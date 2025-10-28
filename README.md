# poderada-farol


### Vídeo do projeto concluido:

https://youtube.com/shorts/qnlXVADWeZc?feature=share  


### Código Utilizado:

```
unsigned long tempoAnterior = 0;
int etapa = 0;

void setup() {
  pinMode(12, OUTPUT);
  pinMode(8, OUTPUT);
  pinMode(10, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  unsigned long tempoAtual = millis();

  switch (etapa) {
    case 0: // LED 12 aceso por 6s
      digitalWrite(12, HIGH);
      if (tempoAtual - tempoAnterior >= 6000) {
        digitalWrite(12, LOW);
        etapa = 1;
        tempoAnterior = tempoAtual;
      }
      break;

    case 1: // LED 8 aceso por 4s
      digitalWrite(8, HIGH);
      if (tempoAtual - tempoAnterior >= 4000) {
        digitalWrite(8, LOW);
        etapa = 2;
        tempoAnterior = tempoAtual;
      }
      break;

    case 2: // LED 10 aceso por 2s
      digitalWrite(10, HIGH);
      if (tempoAtual - tempoAnterior >= 2000) {
        digitalWrite(10, LOW);
        etapa = 0; // reinicia o ciclo
        tempoAnterior = tempoAtual;
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

