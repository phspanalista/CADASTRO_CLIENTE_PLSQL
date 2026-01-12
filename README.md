
# Teste Técnico — Oracle Forms & PL/SQL

## Objetivo
Implementar uma solução simples de cadastro de clientes utilizando Oracle Forms
integrado a uma camada de negócio em PL/SQL, respeitando boas práticas, validações,
tratamento de erros e separação de responsabilidades.

## Stack
- Oracle Database XE 19c / 21c
- Oracle Forms 11g / 12c

## Estrutura do Projeto
/db
  - create.sql
  - drop.sql
  - pkg_cliente.sql

/forms
  - cliente.fmb (design-time)
  - cliente.fmx (runtime)
  - triggers_cliente.sql

## Camada de Banco
- Tabela TB_CLIENTE com constraints e integridade
- Sequence e Trigger para PK
- Validações estruturais no banco

## Camada PL/SQL
- Package PKG_CLIENTE centralizando regras de negócio
- CRUD completo
- Validações de entrada
- RAISE_APPLICATION_ERROR padronizado
- Sem controle transacional interno (commit/rollback)

## Oracle Forms
- Tela de cadastro com fluxo CRUD
- Validações em WHEN-VALIDATE-ITEM
- Botões para Novo, Salvar, Excluir, Cancelar
- Integração exclusiva via package PL/SQL

## Observação Importante
O ambiente local utilizado não possuía o Oracle Forms Builder (Design Time),
apenas runtime/compiler.

Por esse motivo:
- O foco da entrega está na camada de dados e negócio
- As triggers do Forms estão documentadas em arquivo separado
- O módulo pode ser compilado e executado normalmente em ambiente com Builder completo

## Considerações Finais
A solução foi pensada para fácil manutenção, clareza de responsabilidades
e aderência às boas práticas utilizadas em ambientes corporativos.
