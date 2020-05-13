---
title: ICorDebugFunction3 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
ms.openlocfilehash: 71aa482cc2268da17f1376d8c305dd6a818d92d0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213167"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="19f01-102">ICorDebugFunction3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="19f01-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="19f01-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="19f01-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="19f01-104">ICorDebugFunction インターフェイスを論理的に拡張して、ReJIT 要求からコードへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="19f01-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="19f01-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="19f01-105">Methods</span></span>  
  
|<span data-ttu-id="19f01-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="19f01-106">Method</span></span>|<span data-ttu-id="19f01-107">説明</span><span class="sxs-lookup"><span data-stu-id="19f01-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="19f01-108">GetActiveReJitRequestILCode メソッド</span><span class="sxs-lookup"><span data-stu-id="19f01-108">GetActiveReJitRequestILCode Method</span></span>](icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="19f01-109">アクティブな ReJIT 要求から IL を含む、[コード](icordebugilcode-interface.md)へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="19f01-109">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19f01-110">解説</span><span class="sxs-lookup"><span data-stu-id="19f01-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19f01-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="19f01-111">Requirements</span></span>  
 <span data-ttu-id="19f01-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19f01-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19f01-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19f01-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19f01-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19f01-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19f01-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19f01-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19f01-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="19f01-116">See also</span></span>

- [<span data-ttu-id="19f01-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="19f01-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="19f01-118">デバッグ</span><span class="sxs-lookup"><span data-stu-id="19f01-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="19f01-119">ReJIT: ハウツーガイド</span><span class="sxs-lookup"><span data-stu-id="19f01-119">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
