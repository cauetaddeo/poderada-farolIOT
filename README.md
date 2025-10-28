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
