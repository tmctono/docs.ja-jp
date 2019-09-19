---
title: トラブルシューティング:サービス アプリケーションをインストールできない場合
ms.date: 03/30/2017
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
author: ghogen
ms.openlocfilehash: c45ab03ec4577d88953b0e43531082a46c29e8fd
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053531"
---
# <a name="troubleshooting-service-application-wont-install"></a><span data-ttu-id="56e1b-102">トラブルシューティング:サービス アプリケーションをインストールできない場合</span><span class="sxs-lookup"><span data-stu-id="56e1b-102">Troubleshooting: Service Application Won't Install</span></span>
<span data-ttu-id="56e1b-103">サービス アプリケーションが正しくインストールされない場合は、サービス クラスの <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> プロパティが、そのサービスのインストーラーで示されているのと同じ値に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="56e1b-103">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="56e1b-104">サービスが正しくインストールされるためには、両方のインスタンスで同じ値になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="56e1b-104">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="56e1b-105">また、インストール ログを見て、インストール プロセスについてのフィードバックを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="56e1b-105">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="56e1b-106">同じ名前の別のサービスが既にインストールされているかどうかも確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56e1b-106">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="56e1b-107">インストールが成功するには、サービス名が一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="56e1b-107">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56e1b-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="56e1b-108">See also</span></span>

- [<span data-ttu-id="56e1b-109">Windows サービス アプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="56e1b-109">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
