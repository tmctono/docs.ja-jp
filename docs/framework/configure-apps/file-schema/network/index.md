---
title: ネットワーク設定スキーマ
description: .NET Framework がインターネットに接続し、Uri を処理する方法を指定するネットワーク設定のスキーマについて説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- elements [.NET Framework], network configuration elements
- sending data, network configuration elements
- receiving data, network configuration elements
- configuration settings [.NET Framework], networks
- Internet, network configuration elements
- network configuration elements
- network settings
- connections [.NET Framework], network configuration elements
- network resources, network configuration elements
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
ms.openlocfilehash: 8071fcfcdb16b6e71d8d7af05a704d8842b3e963
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158917"
---
# <a name="network-settings-schema"></a>ネットワーク設定スキーマ

ネットワーク設定は、.NET Framework がインターネットに接続する方法を指定します。

この \<system.net> 設定は、.NET Framework がネットワークに接続する方法を指定します。 次の表では、 [ \<system.Net> 要素 (ネットワーク設定)](system-net-element-network-settings.md)の下にある各子構成要素の機能について説明します。  
  
|要素|説明|  
|-------------|-----------------|  
|[\<authenticationModules> 要素 (ネットワーク設定)](authenticationmodules-element-network-settings.md)|インターネット要求の認証に使用されるモジュールを指定します。|  
|[\<connectionManagement> 要素 (ネットワーク設定)](connectionmanagement-element-network-settings.md)|インターネット ホストへの接続の最大数を指定します。|  
|[\<defaultProxy> 要素 (ネットワーク設定)](defaultproxy-element-network-settings.md)|インターネットへの HTTP 要求のために使用するプロキシ サーバーを指定します。|  
|[\<mailSettings> 要素 (ネットワーク設定)](mailsettings-element-network-settings.md)|電子メールの送信オプションの設定が含まれています。|  
|[\<requestCaching> 要素 (ネットワーク設定)](requestcaching-element-network-settings.md)|ネットワーク要求のキャッシュメカニズムを制御します。|  
|[\<webRequestModules> 要素 (ネットワーク設定)](webrequestmodules-element-network-settings.md)|インターネット ホストから情報を要求するために使用するモジュールを指定します。|  
  
この \<uri> 設定は、.NET Framework が uniform resource identifier (uri) を使用して表された web アドレスを処理する方法を指定します。 次の表では、 [ \<uri> 要素 (Uri 設定)](uri-element-uri-settings.md)の下にある各子構成要素の関数について説明します。  
  
|要素|説明|  
|-------------|-----------------|  
|[\<idn> 要素 (Uri 設定)](idn-element-uri-settings.md)|国際化ドメイン名 (IDN) の解析がドメイン名に適用されるかどうかを指定します。|  
|[\<iriParsing> 要素 (Uri 設定)](iriparsing-element-uri-settings.md)|International Resource Identifier (IRI) 解析が、<xref:System.Uri> に適用されるかどうか、および IRI の解析規則が適用されるどうかを指定します。|  
|[\<schemeSettings> 要素 (Uri 設定)](schemesettings-element-uri-settings.md)|<xref:System.Uri> が特定のスキームに解析される方法を指定します。|  
  
## <a name="see-also"></a>関連項目

- [インターネット アプリケーションの構成](../../../network-programming/configuring-internet-applications.md)
- [構成ファイル スキーマ](../index.md)
