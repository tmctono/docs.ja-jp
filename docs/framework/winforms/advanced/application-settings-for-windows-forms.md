---
title: Windows フォームのアプリケーション設定
ms.date: 04/07/2017
f1_keywords:
- ClientApplicationSettings
helpviewer_keywords:
- application settings [Windows Forms]
- Windows Forms, application settings
ms.assetid: 64090a34-8556-4904-8ea0-20efe9f8c886
ms.openlocfilehash: 0cac4433ec9fe54721752c63d2b3b37f9d874c19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779146"
---
# <a name="application-settings-for-windows-forms"></a><span data-ttu-id="a1b02-102">Windows フォームのアプリケーション設定</span><span class="sxs-lookup"><span data-stu-id="a1b02-102">Application Settings for Windows Forms</span></span>
<span data-ttu-id="a1b02-103">Windows フォームのアプリケーション設定の機能により、カスタム アプリケーションと、クライアント上のユーザー設定の作成、保存、および保守が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="a1b02-103">The Applications Settings feature of Windows Forms makes it easy to create, store, and maintain custom application and user preferences on the client.</span></span> <span data-ttu-id="a1b02-104">アプリケーション設定では、データベースの接続文字列など、アプリケーションのデータだけでなく、ツールバーの位置や最近使用した一覧など、ユーザー固有のデータも格納することができます。</span><span class="sxs-lookup"><span data-stu-id="a1b02-104">With Application Settings, you can store not only application data such as database connection strings, but also user-specific data, such as toolbar positions and most-recently used lists.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a1b02-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a1b02-105">In This Section</span></span>  
 [<span data-ttu-id="a1b02-106">アプリケーション設定の概要</span><span class="sxs-lookup"><span data-stu-id="a1b02-106">Application Settings Overview</span></span>](~/docs/framework/winforms/advanced/application-settings-overview.md)  
 <span data-ttu-id="a1b02-107">アプリケーションとユーザーのために設定のデータを作成して格納する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a1b02-107">Discusses how to create and store settings data on behalf of your application and your users.</span></span>  
  
 [<span data-ttu-id="a1b02-108">アプリケーション設定アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="a1b02-108">Application Settings Architecture</span></span>](~/docs/framework/winforms/advanced/application-settings-architecture.md)  
 <span data-ttu-id="a1b02-109">アプリケーション設定機能のしくみについて説明し、グループ化された設定や設定キーなど、アーキテクチャの高度な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="a1b02-109">Describes how the Application Settings feature works, and explores advanced features of the architecture such as grouped settings and settings keys.</span></span>  
  
 [<span data-ttu-id="a1b02-110">アプリケーション設定の属性</span><span class="sxs-lookup"><span data-stu-id="a1b02-110">Application Settings Attributes</span></span>](~/docs/framework/winforms/advanced/application-settings-attributes.md)  
 <span data-ttu-id="a1b02-111">アプリケーションの設定のラッパー クラスまたはその設定のプロパティに適用できる属性を一覧で説明しています。</span><span class="sxs-lookup"><span data-stu-id="a1b02-111">Lists and describes the attributes that can be applied to an application settings wrapper class or its settings properties.</span></span>  
  
 [<span data-ttu-id="a1b02-112">Application Settings for Custom Controls</span><span class="sxs-lookup"><span data-stu-id="a1b02-112">Application Settings for Custom Controls</span></span>](~/docs/framework/winforms/advanced/application-settings-for-custom-controls.md)  
 <span data-ttu-id="a1b02-113">サード パーティ製のアプリケーションでホストされている場合、アプリケーション設定を保存する機能をカスタム コントロールに追加するためにしなければならないことについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a1b02-113">Discusses what must be done to give your custom controls the ability to persist application settings when hosted in third-party applications.</span></span>  
  
 [<span data-ttu-id="a1b02-114">方法: アプリケーション設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="a1b02-114">How to: Create Application Settings</span></span>](~/docs/framework/winforms/advanced/how-to-create-application-settings.md)  
 <span data-ttu-id="a1b02-115">アプリケーション セッション間で永続化される新しいアプリケーション設定を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a1b02-115">Demonstrates creating new application settings that are persisted between application sessions.</span></span>  
  
 [<span data-ttu-id="a1b02-116">方法: アプリケーション設定を検証します。</span><span class="sxs-lookup"><span data-stu-id="a1b02-116">How to: Validate Application Settings</span></span>](~/docs/framework/winforms/advanced/how-to-validate-application-settings.md)  
 <span data-ttu-id="a1b02-117">永続化する前に、アプリケーション設定を検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a1b02-117">Demonstrates validating application settings before they are persisted.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="a1b02-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a1b02-118">Related topics</span></span>

<span data-ttu-id="a1b02-119">[Windows フォームの構成セクション](../../configure-apps/file-schema/winforms/index.md)  </span><span class="sxs-lookup"><span data-stu-id="a1b02-119">[Windows Forms Configuration Section](../../configure-apps/file-schema/winforms/index.md)  </span></span>  
<span data-ttu-id="a1b02-120">.NET Framework 4.7 以降では、Windows フォーム アプリケーションで高 DPI を有効にする設定をサポートするドキュメント。</span><span class="sxs-lookup"><span data-stu-id="a1b02-120">Documents the settings to enable High DPI support in Windows Forms Application starting with the .NET Framework 4.7.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1b02-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1b02-121">See also</span></span>

- [<span data-ttu-id="a1b02-122">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="a1b02-122">Windows Forms</span></span>](../index.md)
