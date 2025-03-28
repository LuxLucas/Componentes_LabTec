## Sensor infra-Vermelho TCRT 5000
![enter image description here](https://www.saravati.com.br/media/catalog/product/cache/ff61517d26ace703648229d56c081b52/9/d/9dcb3c4ac3.jpg)

### Portas Pin


| PIN|VALOR  |
|--|--|
| A0 |ENTRADA ANALÓGICA  |
| D0 |ENTRADA DIGITAL  |
| VGG |POSITIVO (3.3-5V)  |
| GND |NEGATIVO(GND) |


### Funcionamento

 Este modelo é um sensor infravermelho que funciona da seguinte maneira, o led azul

 irá mandar um feixe de luz que ao atingir uma superfície deve retornar ao led preto em

 caso de isto acontecer a porta digital retorna HIGH senão deverá retornar LOW.

 A sensibilidade do feixe pode ser ajustada através do potenciômetro acima do mesmo

 para que ele detecte mais facilmente superfícies não reflexivas e vice-versa.

### Código Exemplo De Teste


  

	void  setup()  {

	Serial.begin(9600);

	}

	  

	void  loop()  {

	//Pega o valor de reflexão caso algo seja refletido o valor sera alto

	int reflection = analogRead(A0);

	//checa se o valor da reflexão esta de acordo com o potenciometro

	bool valid = digitalRead(8);

	Serial.println(reflection);

	//Caso a reflexão seja HIGH ele achou uma superficie desejada do contrario sera LOW

	if(valid == HIGH){

	Serial.println("ACHOU");

	}else{

	Serial.println("FALHOU");

	}

	delay(3000);

	}

