# PIM — Sistema de Gestão de Hospedagem
**Pousada Bela Vista**  
Modelo Independente de Plataforma (Platform Independent Model)  

> dupla: Bianca de Oliveira Schiavo e Emily Pereira Amorim 
---

## 1. Diagrama de Classes

```mermaid
classDiagram
    class Hospede {
        +String cpf
        +String nome
        +String telefone
        +String email
        +buscarPorCPF(cpf) Hospede
        +cadastrar() void
    }

    class CategoriaQuarto {
        +Integer id
        +String nome
        +Decimal precoDiaria
        +calcularDiaria(qtdDias) Decimal
    }

    class Quarto {
        +Integer numero
        +StatusLimpeza statusLimpeza
        +StatusOcupacao statusOcupacao
        +atualizarStatusLimpeza(status) void
        +verificarDisponibilidade(entrada, saida) Boolean
    }

    class Reserva {
        +Integer id
        +Date dataEntrada
        +Date dataSaida
        +StatusReserva status
        +registrarCheckIn() void
        +registrarCheckOut() void
        +cancelar() void
    }

    class ItemConsumo {
        +Integer id
        +String descricao
        +Decimal valor
        +DateTime dataHora
    }

    class Conta {
        +Integer id
        +Decimal totalDiarias
        +Decimal totalConsumos
        +Decimal totalGeral
        +calcularTotal() Decimal
        +fecharConta() void
    }

    Hospede "1" --> "*" Reserva : realiza
    Reserva "*" --> "1" Quarto : ocupa
    Quarto "*" --> "1" CategoriaQuarto : pertence a
    Reserva "1" --> "1" Conta : gera
    Conta "1" --> "*" ItemConsumo : contém
```

---

## 2. Diagrama de Sequência — Check-in

```mermaid
sequenceDiagram
    actor Recepcionista
    participant Sistema
    participant Quarto

    Recepcionista->>Sistema: buscarHospedePorCPF(cpf)
    Sistema-->>Recepcionista: dados do hóspede

    Recepcionista->>Sistema: verificarDisponibilidade(quartoId, datas)
    Sistema->>Quarto: consultarStatus(quartoId)
    Quarto-->>Sistema: statusLimpeza

    alt statusLimpeza = "Sujo"
        Sistema-->>Recepcionista: exibirAlerta("Quarto não está pronto")
    else statusLimpeza = "Limpo"
        Recepcionista->>Sistema: criarReserva(hospede, quarto, datas)
        Sistema-->>Recepcionista: reservaConfirmada(id)

        Recepcionista->>Sistema: registrarCheckIn(reservaId)
        Sistema->>Quarto: atualizarStatus("Ocupado")
        Sistema-->>Recepcionista: checkInConcluído()
    end
```

---

## 3. Diagrama de Estados — Ciclo de vida do Quarto

```mermaid
stateDiagram-v2
    [*] --> Disponivel : quarto cadastrado

    Disponivel --> Reservado : reservar()
    Reservado --> Disponivel : cancelar()

    Reservado --> Ocupado : checkIn()
    Disponivel --> Ocupado : checkIn() direto

    Ocupado --> Sujo : checkOut()

    Sujo --> EmLimpeza : iniciarLimpeza()
    EmLimpeza --> Disponivel : concluirLimpeza()

    Ocupado --> [*] : encerrado

    Disponivel : Disponível
    EmLimpeza : Em limpeza
```

---