# Infraestrutura Profissional com Terraform

Bem-vindo ao repositório de infraestruturas profissionais gerenciadas com Terraform! Este repositório contém configurações e scripts Terraform para provisionamento e gerenciamento de infraestrutura em ambientes de produção.

## Descrição do Projeto

Este repositório tem como objetivo fornecer uma base sólida para a criação, manutenção e escalabilidade de infraestruturas de TI utilizando o Terraform. Com configurações otimizadas e práticas recomendadas, este projeto visa facilitar o trabalho de DevOps e Administradores de Sistemas ao gerenciar recursos em várias plataformas de nuvem.

## Conteúdo

- **Configurações Gerais**: Configurações comuns utilizadas em diferentes cenários de infraestrutura.
- **Ambientes**: Configurações específicas para ambientes de desenvolvimento, homologação e produção.
- **Módulos Reutilizáveis**: Módulos Terraform que podem ser facilmente reutilizados em diferentes projetos.
- **Scripts de Automação**: Scripts para automação de tarefas relacionadas à infraestrutura.
- **Documentação**: Documentação detalhada de cada componente e orientação sobre como utilizá-los.

## Estrutura do Repositório

- `configs/`: Configurações gerais.
- `envs/`: Configurações específicas de cada ambiente.
- `modules/`: Módulos reutilizáveis.
- `scripts/`: Scripts de automação.
- `docs/`: Documentação detalhada e guias de uso.

## Pré-requisitos

- Conta em uma plataforma de nuvem (AWS, Azure, GCP, etc.).
- Terraform instalado ([instruções de instalação](https://www.terraform.io/downloads.html)).
- Conhecimentos básicos de linha de comando e infraestrutura.

## Instalando o Terraform

Para instalar o Terraform, siga os passos abaixo:

1. Baixe o pacote de instalação do [site oficial](https://www.terraform.io/downloads.html).
2. Extraia o conteúdo do pacote.
3. Mova o binário do Terraform para um diretório que está no seu PATH. Por exemplo:
    ```sh
    sudo mv terraform /usr/local/bin/
    ```
4. Verifique a instalação executando:
    ```sh
    terraform --version
    ```

## Comandos Essenciais

- `terraform init`: Inicializa o diretório de trabalho com os arquivos de configuração do Terraform.
- `terraform plan`: Cria um plano de execução mostrando as mudanças que serão aplicadas.
- `terraform apply`: Aplica as mudanças necessárias para alcançar o estado desejado da configuração.
- `terraform destroy`: Destroi a infraestrutura gerenciada pelo Terraform.

## Exemplo Básico

Aqui está um exemplo básico de um script Terraform para provisionar uma instância EC2 na AWS:

```hcl
provider "aws" {
  region = "us-west-2"
}

resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"

  tags = {
    Name = "terraform-example"
  }
}
