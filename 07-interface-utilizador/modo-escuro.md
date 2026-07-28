# Modo Escuro

## Propósito
Definir a implementação do modo escuro na Junta Observatory Platform.

## Cores

| Token | Claro | Escuro |
|---|---|---|
| `--color-bg` | #FFFFFF | #1A1D23 |
| `--color-surface` | #F8F9FA | #2D323B |
| `--color-text` | #212529 | #E4E7EB |
| `--color-text-secondary` | #6C757D | #9BA1AA |
| `--color-border` | #DEE2E6 | #3F444E |

## Implementação

- Variáveis CSS customizadas
- `prefers-color-scheme` para deteção automática
- Toggle manual no cabeçalho
- Persistência da preferência (localStorage)
- Transição suave entre modos (0.3s)

## Documentos Relacionados

- [Sistema de Design](sistema-de-design.md)
- [Acessibilidade](acessibilidade.md)
