---
title: ICLRDebuggingLibraryProvider インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider
helpviewer_keywords:
- ICLRDebuggingLibraryProvider interface [.NET Framework debugging]
ms.assetid: 67739617-6add-41a9-9de5-a3200c3109ce
topic_type:
- apiref
ms.openlocfilehash: a8d9348572ec0cf67c5facebb2053a7091661724
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793595"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="758cb-102">ICLRDebuggingLibraryProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="758cb-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="758cb-103">には、提供[ライブラリのメソッド](iclrdebugginglibraryprovider-providelibrary-method.md)メソッドが含まれています。このメソッドは、共通言語ランタイムのバージョン固有のデバッグライブラリをオンデマンドで検索して読み込むことができるようにする、ライブラリプロバイダーのコールバックインターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="758cb-103">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="758cb-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="758cb-104">Methods</span></span>  
  
|<span data-ttu-id="758cb-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="758cb-105">Method</span></span>|<span data-ttu-id="758cb-106">説明</span><span class="sxs-lookup"><span data-stu-id="758cb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="758cb-107">ProvideLibrary メソッド</span><span class="sxs-lookup"><span data-stu-id="758cb-107">ProvideLibrary Method</span></span>](iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="758cb-108">デバッガーが、デバッグライブラリの読み込みに使用できるモジュールへのハンドルを提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="758cb-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="758cb-109">要件</span><span class="sxs-lookup"><span data-stu-id="758cb-109">Requirements</span></span>  
 <span data-ttu-id="758cb-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="758cb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="758cb-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="758cb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="758cb-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="758cb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="758cb-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="758cb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="758cb-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="758cb-114">See also</span></span>

- [<span data-ttu-id="758cb-115">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="758cb-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="758cb-116">デバッグ</span><span class="sxs-lookup"><span data-stu-id="758cb-116">Debugging</span></span>](index.md)
