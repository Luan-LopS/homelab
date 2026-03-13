# ⚠️ Desafios da instalação

Pode parecer bobeira, mas tive algumas dificuldades durante a instalação, mais especificamente com a **interface gráfica**.

Quando realizamos o boot pelo pendrive e escolhemos em qual disco o sistema será instalado, ao iniciar o processo de boot a interface é praticamente igual à anterior. Por causa disso, fiquei na dúvida se o sistema realmente havia sido instalado e acabei **reinstalando o sistema cerca de três vezes**.

Outro ponto em que tive um certo desafio foi na **configuração inicial do PPPoE**.
O processo em si é simples, porém não fiz corretamente na primeira tentativa. Existe um **mini tutorial** que aparece durante a configuração inicial, e acabei refazendo uma configuração que já existia.

Depois disso, não consegui fazer a conexão funcionar sem precisar **resetar a configuração**. Após realizar o reset e configurar novamente, tudo funcionou normalmente.

### 📌 Observação importante

Somente coloque o **roteador da operadora em modo bridge** depois que o **firewall já estiver configurado com PPPoE**.

No meu caso, quando tentei fazer isso antes da configuração completa no firewall, a conexão não funcionou corretamente.
