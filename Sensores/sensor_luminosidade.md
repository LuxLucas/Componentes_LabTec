
## Sensor de luminosidade (Mh sensor Series Flying-fish)
![enter image description here](https://www.usinainfo.com.br/1034555-thickbox_default/modulo-sensor-de-luminosidade-ldr-4-pinos-saida-digital-e-analogica.jpg)

## Portas Pin


| PIN|VALOR  |
|--|--|
| A0 |ENTRADA ANALÓGICA  |
| D0 |ENTRADA DIGITAL  |
| VGG |POSITIVO (3.3-5V)  |
| GND |NEGATIVO(GND) |


## Funcionamento

 Este modelo é um sensor de luminosidade que usa LM393 que é um módulo que

 compara uma tensão de entrada (que pode ser checada através da porta A0) e uma

 tensão de referência que é obtida através do potenciômetro presente em cima do

 mesmo (Caixa azul), com isto ele retorna uma resposta para o D0 definindo como

 HIGH ou LOW o mesmo.


 O sensor aumenta sua resistência quando está em um ambiente claro e a diminui no

 escuro o que faz com que ao analisar a entrada analógica os valores mais próximos do

 0 signifiquem claro e os valores mais próximos do 1023 signifique escuro.

 É possível se a porta digital está recebendo HIGH ou LOW tanto através do comando

 digitalRead(porta), tanto através do próprio componente que tem um led que quando

 está em estado LOW acende e quando está em estado HIGH se apaga, facilitando o

 ajuste do potenciômetro.

### Código Exemplo De Teste

  

	void  setup()  {

	//Inicia serial

	Serial.begin(9600);

	}

	  

	void  loop()  {

	//Pegar o valor analógico referente a iluminação

	int light = analogRead(A0);

	//Retorna se o valor pego esta igual ou acima do limite definido pelo potenciometro

	bool valid = digitalRead(8);

	Serial.println(light);

	//Quanto mais alto mais escuro então escuro é HIGH e claro LOW

	if(valid == HIGH){

	Serial.println("Escuro");

	}else{

	Serial.println("Claro");

	}

	delay(3000);

	}
