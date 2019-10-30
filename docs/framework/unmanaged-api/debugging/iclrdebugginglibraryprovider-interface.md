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
ms.openlocfilehash: 81b9ffe5979ad553a5bdfbc27111469b2ff4db6f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111374"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="dac78-102">ICLRDebuggingLibraryProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dac78-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="dac78-103">には、提供[ライブラリのメソッド](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)メソッドが含まれています。このメソッドは、共通言語ランタイムのバージョン固有のデバッグライブラリをオンデマンドで検索して読み込むことができるようにする、ライブラリプロバイダーのコールバックインターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="dac78-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dac78-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="dac78-104">Methods</span></span>  
  
|<span data-ttu-id="dac78-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="dac78-105">Method</span></span>|<span data-ttu-id="dac78-106">説明</span><span class="sxs-lookup"><span data-stu-id="dac78-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dac78-107">ProvideLibrary メソッド</span><span class="sxs-lookup"><span data-stu-id="dac78-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="dac78-108">デバッガーが、デバッグライブラリの読み込みに使用できるモジュールへのハンドルを提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="dac78-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dac78-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="dac78-109">Requirements</span></span>  
 <span data-ttu-id="dac78-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dac78-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dac78-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dac78-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dac78-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dac78-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dac78-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dac78-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dac78-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="dac78-114">See also</span></span>

- [<span data-ttu-id="dac78-115">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dac78-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="dac78-116">デバッグ</span><span class="sxs-lookup"><span data-stu-id="dac78-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
