---
title: Tlbexp ヘルパー関数 (アンマネージ API リファレンス)
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
ms.openlocfilehash: cbde2af9c8a03e6c41f571120027030713f1b8d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "73104123"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="20759-102">Tlbexp ヘルパー関数 (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="20759-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="20759-103">[タイプ ライブラリ エクスポーター ツール](../../tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) により、TlbRef.dll という名前のダイナミック リンク ライブラリが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="20759-103">The [Type Library Exporter tool](../../tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="20759-104">この DLL には、エクスポーター ツールによってアセンブリからタイプ ライブラリへの変換処理中に使用される、2 つのヘルパー関数とインターフェイスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="20759-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20759-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="20759-105">In This Section</span></span>  
 [<span data-ttu-id="20759-106">GetTypeLibInfo 関数</span><span class="sxs-lookup"><span data-stu-id="20759-106">GetTypeLibInfo Function</span></span>](gettypelibinfo-function.md)  
 <span data-ttu-id="20759-107">タイプ ライブラリのローカライズとオペレーティング システムに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="20759-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="20759-108">LoadTypeLibWithResolver 関数</span><span class="sxs-lookup"><span data-stu-id="20759-108">LoadTypeLibWithResolver Function</span></span>](loadtypelibwithresolver-function.md)  
 <span data-ttu-id="20759-109">[ITypeLibResolver インターフェイス](itypelibresolver-interface.md)の実装を使ってタイプ ライブラリを読み込み、参照されたあらゆるタイプ ライブラリを解決します。</span><span class="sxs-lookup"><span data-stu-id="20759-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="20759-110">ITypeLibResolver インターフェイス</span><span class="sxs-lookup"><span data-stu-id="20759-110">ITypeLibResolver Interface</span></span>](itypelibresolver-interface.md)  
 <span data-ttu-id="20759-111">タイプ ライブラリの完全修飾パスを返す、[ResolveTypeLib メソッド](resolvetypelib-method.md)を提供します。</span><span class="sxs-lookup"><span data-stu-id="20759-111">Provides the [ResolveTypeLib method](resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>
