---
title: スタートアップ設定スキーマ
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
ms.openlocfilehash: e5f9c9af64ff38e7c0f1f26ccab039261b052e30
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "61701516"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="bd88a-102">スタートアップ設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="bd88a-102">Startup settings schema</span></span>

<span data-ttu-id="bd88a-103">スタートアップ設定は、アプリケーションを実行する必要のある共通言語ランタイムのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="bd88a-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="bd88a-104">要素</span><span class="sxs-lookup"><span data-stu-id="bd88a-104">Element</span></span>|<span data-ttu-id="bd88a-105">説明</span><span class="sxs-lookup"><span data-stu-id="bd88a-105">Description</span></span>|  
|-------------|-----------------|  
|[\<requiredRuntime>](requiredruntime-element.md)|<span data-ttu-id="bd88a-106">バージョン 1.0 の共通言語ランタイムのみがアプリケーションでサポートされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="bd88a-106">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="bd88a-107">ランタイムバージョン1.1 でビルドされたアプリケーションでは、要素を使用する必要があり **\<supportedRuntime>** ます。</span><span class="sxs-lookup"><span data-stu-id="bd88a-107">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[\<supportedRuntime>](supportedruntime-element.md)|<span data-ttu-id="bd88a-108">アプリケーションでサポートされる共通言語ランタイムのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="bd88a-108">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[\<startup>](startup-element.md)|<span data-ttu-id="bd88a-109">要素と要素が含まれてい **\<requiredRuntime>** **\<supportedRuntime>** ます。</span><span class="sxs-lookup"><span data-stu-id="bd88a-109">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd88a-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd88a-110">See also</span></span>

- [<span data-ttu-id="bd88a-111">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="bd88a-111">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="bd88a-112">方法: .NET Framework 4 以降のバージョンをサポートするアプリを構成する</span><span class="sxs-lookup"><span data-stu-id="bd88a-112">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
