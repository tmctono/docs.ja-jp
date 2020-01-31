---
title: ICLRDebugging インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging
helpviewer_keywords:
- ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type:
- apiref
ms.openlocfilehash: 9a768535c3bf69b5127777de4cee27054943091d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793641"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="81af1-102">ICLRDebugging インターフェイス</span><span class="sxs-lookup"><span data-stu-id="81af1-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="81af1-103">デバッグ用にモジュールの読み込みとアンロードを処理するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="81af1-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="81af1-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="81af1-104">Methods</span></span>  
  
|<span data-ttu-id="81af1-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="81af1-105">Method</span></span>|<span data-ttu-id="81af1-106">説明</span><span class="sxs-lookup"><span data-stu-id="81af1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="81af1-107">OpenVirtualProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="81af1-107">OpenVirtualProcess Method</span></span>](iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="81af1-108">プロセスに読み込まれた共通言語ランタイム (CLR) モジュールに対応する "のプロセス" インターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="81af1-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="81af1-109">CanUnloadNow メソッド</span><span class="sxs-lookup"><span data-stu-id="81af1-109">CanUnloadNow Method</span></span>](iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="81af1-110">[ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md)インターフェイスによって提供されたライブラリがまだ使用中であるか、またはアンロードできるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="81af1-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81af1-111">コメント</span><span class="sxs-lookup"><span data-stu-id="81af1-111">Remarks</span></span>  
 <span data-ttu-id="81af1-112">`ICLRDebugging` インターフェイスのインスタンスを取得するには、 [Clrcreateinstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="81af1-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81af1-113">要件</span><span class="sxs-lookup"><span data-stu-id="81af1-113">Requirements</span></span>  
 <span data-ttu-id="81af1-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81af1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81af1-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81af1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81af1-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81af1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81af1-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81af1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81af1-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="81af1-118">See also</span></span>

- [<span data-ttu-id="81af1-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="81af1-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="81af1-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="81af1-120">Debugging</span></span>](index.md)
