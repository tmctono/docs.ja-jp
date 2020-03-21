---
title: アプリケーションの設定
ms.date: 04/07/2017
f1_keywords:
- ClientApplicationSettings
helpviewer_keywords:
- application settings [Windows Forms]
- Windows Forms, application settings
ms.assetid: 64090a34-8556-4904-8ea0-20efe9f8c886
ms.openlocfilehash: bd5e03d0277d656be4c6b0e45142279b3e9ec4b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142448"
---
# <a name="application-settings-for-windows-forms"></a><span data-ttu-id="de227-102">Windows フォームのアプリケーション設定</span><span class="sxs-lookup"><span data-stu-id="de227-102">Application Settings for Windows Forms</span></span>
<span data-ttu-id="de227-103">Windows フォームのアプリケーション設定の機能により、カスタム アプリケーションと、クライアント上のユーザー設定の作成、保存、および保守が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="de227-103">The Applications Settings feature of Windows Forms makes it easy to create, store, and maintain custom application and user preferences on the client.</span></span> <span data-ttu-id="de227-104">アプリケーション設定では、データベースの接続文字列など、アプリケーションのデータだけでなく、ツールバーの位置や最近使用した一覧など、ユーザー固有のデータも格納することができます。</span><span class="sxs-lookup"><span data-stu-id="de227-104">With Application Settings, you can store not only application data such as database connection strings, but also user-specific data, such as toolbar positions and most-recently used lists.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="de227-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="de227-105">In This Section</span></span>  
 [<span data-ttu-id="de227-106">アプリケーション設定の概要</span><span class="sxs-lookup"><span data-stu-id="de227-106">Application Settings Overview</span></span>](application-settings-overview.md)  
 <span data-ttu-id="de227-107">アプリケーションとユーザーのために設定のデータを作成して格納する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="de227-107">Discusses how to create and store settings data on behalf of your application and your users.</span></span>  
  
 [<span data-ttu-id="de227-108">Application Settings Architecture</span><span class="sxs-lookup"><span data-stu-id="de227-108">Application Settings Architecture</span></span>](application-settings-architecture.md)  
 <span data-ttu-id="de227-109">アプリケーション設定機能のしくみについて説明し、グループ化された設定や設定キーなど、アーキテクチャの高度な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="de227-109">Describes how the Application Settings feature works, and explores advanced features of the architecture such as grouped settings and settings keys.</span></span>  
  
 [<span data-ttu-id="de227-110">アプリケーション設定の属性</span><span class="sxs-lookup"><span data-stu-id="de227-110">Application Settings Attributes</span></span>](application-settings-attributes.md)  
 <span data-ttu-id="de227-111">アプリケーションの設定のラッパー クラスまたはその設定のプロパティに適用できる属性を一覧で説明しています。</span><span class="sxs-lookup"><span data-stu-id="de227-111">Lists and describes the attributes that can be applied to an application settings wrapper class or its settings properties.</span></span>  
  
 [<span data-ttu-id="de227-112">カスタム コントロールのアプリケーション設定</span><span class="sxs-lookup"><span data-stu-id="de227-112">Application Settings for Custom Controls</span></span>](application-settings-for-custom-controls.md)  
 <span data-ttu-id="de227-113">サード パーティ製のアプリケーションでホストされている場合、アプリケーション設定を保存する機能をカスタム コントロールに追加するためにしなければならないことについて説明します。</span><span class="sxs-lookup"><span data-stu-id="de227-113">Discusses what must be done to give your custom controls the ability to persist application settings when hosted in third-party applications.</span></span>  
  
 [<span data-ttu-id="de227-114">方法 : アプリケーション設定を作成する</span><span class="sxs-lookup"><span data-stu-id="de227-114">How to: Create Application Settings</span></span>](how-to-create-application-settings.md)  
 <span data-ttu-id="de227-115">アプリケーション セッション間で永続化される新しいアプリケーション設定を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="de227-115">Demonstrates creating new application settings that are persisted between application sessions.</span></span>  
  
 [<span data-ttu-id="de227-116">方法 : アプリケーション設定を検証する</span><span class="sxs-lookup"><span data-stu-id="de227-116">How to: Validate Application Settings</span></span>](how-to-validate-application-settings.md)  
 <span data-ttu-id="de227-117">永続化する前に、アプリケーション設定を検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="de227-117">Demonstrates validating application settings before they are persisted.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="de227-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="de227-118">Related topics</span></span>

<span data-ttu-id="de227-119">[Windows フォームの構成セクション](../../configure-apps/file-schema/winforms/index.md).NET Framework 4.7 以降の Windows フォーム アプリケーションで高 DPI サポートを有効にするための設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="de227-119">[Windows Forms Configuration Section](../../configure-apps/file-schema/winforms/index.md) Documents the settings to enable High DPI support in Windows Forms Application starting with the .NET Framework 4.7.</span></span>

## <a name="see-also"></a><span data-ttu-id="de227-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="de227-120">See also</span></span>

- [<span data-ttu-id="de227-121">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="de227-121">Windows Forms</span></span>](../index.md)
