---
title: Tlbexp ヘルパー関数 (アンマネージ API リファレンス)
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f41a233e9b5338bdb0a324ff9af267a97821d4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967701"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="0f493-102">Tlbexp ヘルパー関数 (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="0f493-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="0f493-103">[タイプ ライブラリ エクスポーター ツール](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) により、TlbRef.dll という名前のダイナミック リンク ライブラリが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="0f493-103">The [Type Library Exporter tool](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="0f493-104">この DLL には、エクスポーター ツールによってアセンブリからタイプ ライブラリへの変換処理中に使用される、2 つのヘルパー関数とインターフェイスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0f493-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0f493-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0f493-105">In This Section</span></span>  
 [<span data-ttu-id="0f493-106">GetTypeLibInfo 関数</span><span class="sxs-lookup"><span data-stu-id="0f493-106">GetTypeLibInfo Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 <span data-ttu-id="0f493-107">タイプ ライブラリのローカライズとオペレーティング システムに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="0f493-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="0f493-108">LoadTypeLibWithResolver 関数</span><span class="sxs-lookup"><span data-stu-id="0f493-108">LoadTypeLibWithResolver Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 <span data-ttu-id="0f493-109">[ITypeLibResolver インターフェイス](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)の実装を使ってタイプ ライブラリを読み込み、参照されたあらゆるタイプ ライブラリを解決します。</span><span class="sxs-lookup"><span data-stu-id="0f493-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="0f493-110">ITypeLibResolver インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0f493-110">ITypeLibResolver Interface</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 <span data-ttu-id="0f493-111">タイプ ライブラリの完全修飾パスを返す、[ResolveTypeLib メソッド](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md)を提供します。</span><span class="sxs-lookup"><span data-stu-id="0f493-111">Provides the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>
