---
title: トラブルシューティング:サービス アプリケーションをインストールできない場合
description: サービス アプリケーションをインストールできない場合には、トラブルシューティングを行います。 サービスクラスの ServiceName プロパティが正しく設定されていることを確認します。
ms.date: 03/30/2017
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
ms.openlocfilehash: d606adc7fddeb9f7e76a6974699c2455eda084b2
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608882"
---
# <a name="troubleshooting-service-application-wont-install"></a>トラブルシューティング:サービス アプリケーションをインストールできない場合
サービス アプリケーションが正しくインストールされない場合は、サービス クラスの <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> プロパティが、そのサービスのインストーラーで示されているのと同じ値に設定されていることを確認します。 サービスが正しくインストールされるためには、両方のインスタンスで同じ値になっている必要があります。  
  
> [!NOTE]
> また、インストール ログを見て、インストール プロセスについてのフィードバックを確認することもできます。  
  
 同じ名前の別のサービスが既にインストールされているかどうかも確認する必要があります。 インストールが成功するには、サービス名が一意である必要があります。  
  
## <a name="see-also"></a>関連項目

- [Windows サービス アプリケーションの概要](introduction-to-windows-service-applications.md)
