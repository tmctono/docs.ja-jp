---
title: ICorDebugILFrame2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2
helpviewer_keywords:
- ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4f57f27ec92e7977b46ebfa5967b0590674d2a1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946472"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="777cd-102">ICorDebugILFrame2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="777cd-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="777cd-103">ICorDebugILFrame インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="777cd-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="777cd-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="777cd-104">Methods</span></span>  
  
|<span data-ttu-id="777cd-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="777cd-105">Method</span></span>|<span data-ttu-id="777cd-106">説明</span><span class="sxs-lookup"><span data-stu-id="777cd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="777cd-107">EnumerateTypeParameters メソッド</span><span class="sxs-lookup"><span data-stu-id="777cd-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="777cd-108">含む ICorDebugTypeEnum オブジェクトを取得、<xref:System.Type>このフレーム内のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="777cd-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="777cd-109">RemapFunction メソッド</span><span class="sxs-lookup"><span data-stu-id="777cd-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="777cd-110">新しい MSIL オフセットを指定することで編集された関数を再マップします。</span><span class="sxs-lookup"><span data-stu-id="777cd-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="777cd-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="777cd-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="777cd-112">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="777cd-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="777cd-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="777cd-113">Requirements</span></span>  
 <span data-ttu-id="777cd-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="777cd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="777cd-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="777cd-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="777cd-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="777cd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="777cd-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="777cd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="777cd-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="777cd-118">See also</span></span>

- [<span data-ttu-id="777cd-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="777cd-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
