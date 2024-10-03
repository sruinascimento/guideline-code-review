# Guideline para Revisão de Código

## 1. Funcionalidade
- **Cobertura de Requisitos**: Verifique se o código atende às especificações e aos requisitos definidos.
- **Testes**: Há testes unitários e/ou de integração adequados? Verifique se os cenários relevantes estão cobertos.
- **Comportamento**: Execute os testes (se possível), e garanta que o código novo ou alterado não quebre funcionalidades existentes.

## 2. Boas Práticas de Java
- **Nomenclatura**: Variáveis, métodos e classes devem ter nomes claros e descritivos (camelCase para variáveis e métodos, PascalCase para classes).
- **SOLID**: Verifique a aderência aos princípios SOLID.
- **Exceções**: Erros são tratados corretamente? Evite `throws Exception` genéricos e prefira exceções específicas.
- **Imutabilidade**: Use objetos imutáveis sempre que possível.
- **Coleções**: Verifique se coleções são inicializadas corretamente (evite `null` e prefira coleções vazias).

## 3. Arquitetura Spring
- **Injeção de Dependência**: Use `@Autowired` ou construtores para injeção de dependências.
- **Configurações**: Verifique se as configurações no `application.properties` ou `application.yml` seguem boas práticas, como o uso de placeholders e perfis de ambiente.
- **Controller**: As rotas e métodos estão coerentes com as boas práticas REST? Garanta que os endpoints tenham responsabilidades claras.
- **Service Layer**: A lógica de negócios está encapsulada corretamente em services? Mantenha o Controller leve.
- **Repository**: Valide o uso correto do JPA e consultas SQL, garantindo que consultas complexas estão otimizadas e seguras contra injeção de SQL.

## 4. Banco de Dados (MySQL)
- **Consultas**: Verifique o uso correto de consultas e suas eficiências (evite `N+1` queries, por exemplo).
- **Transações**: As transações estão sendo usadas adequadamente?
- **Migration**: Verifique se há scripts de migração (como Flyway ou Liquibase) para alterações de banco.
- **Índices**: Verifique se os índices estão sendo utilizados corretamente para melhorar a performance das consultas.

## 5. AWS
- **Serviços**: Certifique-se de que os serviços AWS (S3, RDS, Lambda, etc.) estão sendo usados corretamente e com segurança.
- **Autenticação e Autorização**: Verifique se os princípios de segurança (IAM, chaves) estão sendo respeitados.
- **Logs e Monitoramento**: As integrações com CloudWatch, X-Ray ou outra ferramenta de monitoramento estão configuradas corretamente?

## 6. Boas Práticas Gerais
- **Legibilidade**: O código está legível, com formatação consistente e fácil de entender?
- **Comentários**: Verifique se há comentários explicando código complexo, mas evite comentários desnecessários em trechos autoexplicativos.
- **DRY (Don’t Repeat Yourself)**: Certifique-se de que o código não está duplicado.
- **KISS (Keep It Simple, Stupid)**: O código é o mais simples possível para resolver o problema?
- **Performance**: Há otimizações a serem feitas em relação ao desempenho? Verifique uso desnecessário de loops aninhados, processamento pesado em partes críticas, etc.

## 7. Segurança
- **Validação de Dados**: As entradas estão sendo validadas corretamente? (ex: inputs HTTP, consultas SQL, etc.)
- **Autenticação e Autorização**: A API protege dados sensíveis? As permissões estão adequadas?
- **Criptografia**: Verifique o uso de TLS, criptografia de dados sensíveis (como senhas), e segurança nas interações com serviços AWS.

## 8. Ferramentas e Integração com IntelliJ
- **Análise Estática**: Use ferramentas como SonarLint para detectar problemas de código dentro da IDE.
- **Formatador de Código**: Utilize o formatador de código do IntelliJ para garantir uma formatação consistente.
- **Inspeções**: Configure o IntelliJ para realizar inspeções automáticas de código, como detecção de variáveis não utilizadas ou potenciais bugs.
- **Jenkins**: Verifique se os testes e builds automáticos estão funcionando corretamente após a submissão do código.
