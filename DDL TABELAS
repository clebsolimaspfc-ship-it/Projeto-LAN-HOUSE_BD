CREATE TABLE `administrador` (
  `idAdministrador` int NOT NULL AUTO_INCREMENT,
  `nome` varchar(100) DEFAULT NULL,
  `email` varchar(100) DEFAULT NULL,
  `senha_hash` varchar(255) DEFAULT NULL,
  `nivel_acesso` varchar(20) DEFAULT NULL,
  `ultimo_login` datetime DEFAULT NULL,
  PRIMARY KEY (`idAdministrador`),
  UNIQUE KEY `email_UNIQUE` (`email`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3

  CREATE TABLE `audit_log` (
  `idAudit_log` int NOT NULL AUTO_INCREMENT,
  `tabela_afetada` varchar(100) DEFAULT NULL,
  `acao` varchar(20) DEFAULT NULL,
  `descricao` text,
  `ip_origem` varchar(45) DEFAULT NULL,
  `data_evento` datetime DEFAULT NULL,
  `id_cliente` int DEFAULT NULL,
  `Id_administrador` int DEFAULT NULL,
  PRIMARY KEY (`idAudit_log`),
  KEY `fk_cliente_audit_log_idx` (`id_cliente`),
  KEY `fk_administrador_audit_log_idx` (`Id_administrador`),
  CONSTRAINT `fk_administrador_audit_log` FOREIGN KEY (`Id_administrador`) REFERENCES `administrador` (`idAdministrador`),
  CONSTRAINT `fk_cliente_audit_log` FOREIGN KEY (`id_cliente`) REFERENCES `cliente` (`idCliente`) ON DELETE RESTRICT
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3

  CREATE TABLE `cliente` (
  `idCliente` int NOT NULL AUTO_INCREMENT,
  `nome` varchar(100) NOT NULL,
  `cpf` char(14) NOT NULL,
  `email` varchar(100) NOT NULL,
  `telefone` varchar(20) NOT NULL,
  `data_cadastro` datetime NOT NULL,
  PRIMARY KEY (`idCliente`),
  UNIQUE KEY `email_UNIQUE` (`email`),
  UNIQUE KEY `cpf_UNIQUE` (`cpf`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3

  CREATE TABLE `computador` (
  `idComputador` int NOT NULL AUTO_INCREMENT,
  `nome` varchar(50) DEFAULT NULL,
  `especificacao` text,
  `status` varchar(10) DEFAULT NULL,
  `preco_hora` decimal(10,2) DEFAULT NULL,
  PRIMARY KEY (`idComputador`),
  UNIQUE KEY `nome_UNIQUE` (`nome`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3

CREATE TABLE `consumo` (
  `idconsumo` int NOT NULL AUTO_INCREMENT,
  `quantidade` int DEFAULT NULL,
  `subtotal` decimal(10,2) DEFAULT NULL,
  `data_consumo` datetime DEFAULT NULL,
  `id_sessao` int DEFAULT NULL,
  `id_forma_pagamento` int DEFAULT NULL,
  `id_produto` int DEFAULT NULL,
  PRIMARY KEY (`idconsumo`),
  KEY `fk_Sessao_consumo_idx` (`id_sessao`),
  KEY `fk_forma_pagamento_consumo_idx` (`id_forma_pagamento`),
  KEY `fk_produto_consumo_idx` (`id_produto`),
  CONSTRAINT `fk_forma_pagamento_consumo` FOREIGN KEY (`id_forma_pagamento`) REFERENCES `forma_pagamento` (`idforma_pagamento`) ON DELETE RESTRICT,
  CONSTRAINT `fk_produto_consumo` FOREIGN KEY (`id_produto`) REFERENCES `produto` (`idProduto`) ON DELETE RESTRICT,
  CONSTRAINT `fk_Sessao_consumo` FOREIGN KEY (`id_sessao`) REFERENCES `sessao` (`idSessoe`) ON DELETE RESTRICT
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3

  CREATE TABLE `forma_pagamento` (
  `idforma_pagamento` int NOT NULL,
  `nome` varchar(45) DEFAULT NULL,
  `descricao` text,
  PRIMARY KEY (`idforma_pagamento`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3

  CREATE TABLE `inscricao` (
  `idInscricao` int NOT NULL AUTO_INCREMENT,
  `data_inscricao` datetime DEFAULT NULL,
  `Id_torneio` int DEFAULT NULL,
  `id_cliente` int DEFAULT NULL,
  PRIMARY KEY (`idInscricao`),
  KEY `fk_inscricao_torneio_idx` (`Id_torneio`),
  KEY `fk_cliente_inscricao_idx` (`id_cliente`),
  CONSTRAINT `fk_cliente_inscricao` FOREIGN KEY (`id_cliente`) REFERENCES `cliente` (`idCliente`) ON DELETE RESTRICT,
  CONSTRAINT `fk_inscricao_torneio` FOREIGN KEY (`Id_torneio`) REFERENCES `torneio` (`idtorneio`) ON DELETE RESTRICT
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3

  CREATE TABLE `produto` (
  `idProduto` int NOT NULL,
  `nome` varchar(100) DEFAULT NULL,
  `preco` decimal(10,2) DEFAULT NULL,
  `estoque` int DEFAULT NULL,
  `categoria` varchar(100) DEFAULT NULL,
  PRIMARY KEY (`idProduto`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3

  CREATE TABLE `sessao` (
  `idSessoe` int NOT NULL AUTO_INCREMENT,
  `inicio` datetime DEFAULT NULL,
  `fim` datetime DEFAULT NULL,
  `valor_total` decimal(10,2) DEFAULT NULL,
  `status` varchar(10) DEFAULT NULL,
  `id_cliente` int DEFAULT NULL,
  `id_computador` int DEFAULT NULL,
  PRIMARY KEY (`idSessoe`),
  KEY `fk_cliente_sessao_idx` (`id_cliente`),
  KEY `fk_computador_sessao_idx` (`id_computador`),
  CONSTRAINT `fk_cliente_sessao` FOREIGN KEY (`id_cliente`) REFERENCES `cliente` (`idCliente`) ON DELETE RESTRICT,
  CONSTRAINT `fk_computador_sessao` FOREIGN KEY (`id_computador`) REFERENCES `computador` (`idComputador`) ON DELETE RESTRICT
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3

 CREATE TABLE `torneio` (
  `idtorneio` int NOT NULL AUTO_INCREMENT,
  `nome` varchar(100) DEFAULT NULL,
  `jogo` varchar(100) DEFAULT NULL,
  `data_torneio` datetime DEFAULT NULL,
  `premio` decimal(10,2) DEFAULT NULL,
  `descricao` text,
  PRIMARY KEY (`idtorneio`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3
  
  
