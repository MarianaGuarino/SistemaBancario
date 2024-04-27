Este projeto consiste em uma simulação de um sistema bancário onde clientes realizam compras em lojas e funcionários recebem seus salários. O código é escrito em Java e consiste em cinco classes principais:

- `Banco.java`: Implementa a lógica de transferência entre contas bancárias.
- `Cliente.java`: Representa um cliente que realiza compras em lojas.
- `Conta.java`: Define a estrutura de uma conta bancária.
- `Funcionario.java`: Modela um funcionário que recebe salário e pode investir parte dele.
- `Loja.java`: Representa uma loja que realiza pagamentos de salários aos seus funcionários.

FUNCIONALIDADES:

- Transferência de dinheiro entre contas.
- Clientes realizam compras em lojas.
- Funcionários recebem salários e investem parte deles.
- Lojas realizam o pagamento de salários aos funcionários.

BANCO

A classe Banco fornece um método estático transferir para transferir fundos entre duas contas. A classe Banco fornece um método estático chamado transferir para transferir fundos entre duas contas. Vamos examinar como esse método é implementado: Este método recebe três parâmetros:

1 origem: A conta de onde os fundos serão retirados.

2 destino: A conta para onde os fundos serão transferidos.

3 valor: O valor a ser transferido entre as contas.


CLIENTE

A classe Cliente representa um cliente que pode fazer compras em duas lojas diferentes. Ele seleciona aleatoriamente uma loja para fazer uma compra e, se tiver saldo suficiente, realiza a transação. Este cliente é executado em uma thread separada.


CONTA

A classe Conta em Java representa uma conta bancária e possui funcionalidades para manipular o saldo, como depositar, sacar e obter o saldo atual.

Métodos:
depositar(double valor): Adiciona um valor ao saldo da conta.
sacar(double valor): Subtrai um valor do saldo da conta.
getNomeConta(): Retorna o nome da conta.
getSaldo(): Retorna o saldo atual da conta.

Funcionalidades:
Permite depositar e sacar dinheiro da conta de forma segura, utilizando sincronização para evitar problemas de concorrência.
Armazena o nome da conta e o saldo atual.
Utiliza métodos sincronizados para garantir que as operações de depósito e saque sejam thread-safe, evitando condições de corrida.

Uso:
Criar instâncias de Conta para representar diferentes contas bancárias no sistema.
Realizar operações de depósito e saque nas contas dos clientes e funcionários.

LOJA

A classe Loja representa uma loja com um saldo inicial e métodos para exibir saldo final e pagar funcionários. Cada loja tem dois funcionários associados. Funcionamento:

1 Inicialização: Ao ser criada, recebe um nome e um saldo inicial, além de duas instâncias de funcionário associadas.

2 Exibição de Saldo: Oferece um método para exibir o saldo final da loja.

3 Pagamento de Funcionários: Possui um método para pagar os salários dos funcionários, desde que haja saldo suficiente na conta da loja.

Exemplo de uso:

```java
public class Main {
    public static void main(String[] args) {
        // Criação de contas, clientes, funcionários e lojas
        
        Banco banco = new Banco();
        
        // Iniciar threads de clientes
        for (int i = 0; i < numClientes; i++) {
            new Cliente("Cliente " + i, contaCliente, lojas, banco).start();
        }
        
        // Iniciar threads de funcionários
        for (int i = 0; i < numFuncionarios; i++) {
            new Funcionario("Funcionario " + i, contaSalario, contaInvestimento).start();
        }
    }
}
