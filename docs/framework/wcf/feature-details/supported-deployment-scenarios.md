---
title: サポートされている展開シナリオ
ms.date: 03/30/2017
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
ms.openlocfilehash: 299c8f2e29806a123e0a8b6e1e70d8cc13daa7bf
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546251"
---
# <a name="supported-deployment-scenarios"></a>サポートされている展開シナリオ

部分的に信頼されたアプリケーションでの使用がサポートされている Windows Communication Foundation (WCF) 機能のサブセットは、WCF を使用する場合のすべてではなく、一部のシナリオの要件を満たすように設計されています。 サーバーでは、WCF は、セキュリティ上の理由から、ASP.NET 2.0 Medium Trust アクセス許可セットでサードパーティ製アプリケーションを実行するインターネット規模の共有ホスティングプロバイダーの要件を満たしています。 クライアントでは、WCF 部分信頼のサポートは、 [ClickOnce 配置](/visualstudio/deployment/clickonce-security-and-deployment) や WPF の XAML ブラウザーアプリケーションテクノロジなどの配置テクノロジの要件を満たすように設計されています。これにより、信頼されていないサイトからのデスクトップアプリケーションのシームレスで安全な展開が可能になります。

## <a name="minimum-permission-requirements"></a>最小アクセス許可の要件

WCF では、次の標準の名前付きアクセス許可セットのいずれかで実行されるアプリケーションの機能のサブセットをサポートしています。

- 中程度の信頼アクセス許可

- インターネット ゾーン アクセス許可

部分的に信頼されたアプリケーションで、より制限の厳しい権限で WCF を使用しようとすると、実行時にセキュリティ例外が発生する可能性があります。

このようなアクセス許可セットでサポートされる機能の詳細については、「 [Partial Trust Feature Compatibility](partial-trust-feature-compatibility.md)」を参照してください。

## <a name="partial-trust-on-the-server"></a>サーバー上の部分信頼

ASP.NET Web アプリケーションホスティングサービスの多くの商用プロバイダーは、サーバー上で実行されているアプリケーションが ASP.NET 2.0 Medium Trust アクセス許可セットで実行されることを義務付けています。 WCF サービスは、、、 <xref:System.ServiceModel.BasicHttpBinding> <xref:System.ServiceModel.WebHttpBinding> またはをトランスポートレベルのセキュリティで使用している場合に、これらの環境で実行でき <xref:System.ServiceModel.WSHttpBinding> ます。

中程度の信頼のホスト環境で実行されている WCF サービスは、クライアント要求への応答として他のサーバーにメッセージを送信することで、中間層サービスとして機能することもできます。 ホスティング環境が適切な <xref:System.Net.WebPermission> をアプリケーションに与えて、目的のサーバーに送信要求を行うようにする場合は、サーバーでの中間層のシナリオがサポートされます。

サポートされている SOAP バインディングのいずれかを使用する SOAP メッセージングに加えて、WCF では、 <xref:System.ServiceModel.WebHttpBinding> 部分的に信頼されたアプリケーションで Web スタイルのサービスを構築するためのをサポートしています。 Wcf [WEB HTTP プログラミングモデル](wcf-web-http-programming-model.md)、wcf [配信](wcf-syndication.md)、および [AJAX の統合と JSON のサポート](ajax-integration-and-json-support.md) 機能は、すべて部分信頼でサポートされています。

ワークフロー サービスは完全信頼のアクセス許可を必要とし、部分的に信頼されたアプリケーションでは使用できません。

詳細については、「 [方法: ASP.NET 2.0 で中程度の信頼を使用する](/previous-versions/msp-n-p/ff648344(v=pandp.10))」を参照してください。

## <a name="partial-trust-on-the-client"></a>クライアントでの部分信頼

信頼されていないインターネット サイトからコードをダウンロードして実行する場合、ある程度のセキュリティ対策が必要です。 [ClickOnce 配置](/visualstudio/deployment/clickonce-security-and-deployment)と WPF の XAML ブラウザーアプリケーション (XBAP) テクノロジはどちらも、部分信頼を使用して、信頼されていないコードに制限付きのアクセス許可 (インターネットゾーン) を付与します。

WCF を使用すると、 [ClickOnce 配置](/visualstudio/deployment/clickonce-security-and-deployment) または XBAP によって配置された部分信頼アプリケーション内からリモートサーバーと通信できます。 インターネットゾーンのアクセス許可セットには、元のホスト用のが含まれています <xref:System.Net.WebPermission> 。これにより、これらのアプリケーションは、「 [部分信頼機能の互換性](partial-trust-feature-compatibility.md)」で説明されているサポート対象の WCF バインディングを使用して、配信元サーバーと通信できます。

## <a name="see-also"></a>関連項目

- [コード アクセス セキュリティ](../../misc/code-access-security.md)
- [Windows Presentation Foundation ブラウザーによってホストされるアプリケーションの概要](/dotnet/desktop/wpf/app-development/wpf-xaml-browser-applications-overview)
- [部分信頼](partial-trust.md)
- [ASP.NET の信頼レベルとポリシー ファイル](/previous-versions/wyts434y(v=vs.140))
