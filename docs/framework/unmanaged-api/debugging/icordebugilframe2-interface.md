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
ms.openlocfilehash: d02dab01eca3bd4f8ce3ae7ace7f9d4be8233dca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917004"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="d6481-102">ICorDebugILFrame2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d6481-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="d6481-103">モジュールの論理拡張機能インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="d6481-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d6481-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="d6481-104">Methods</span></span>  
  
|<span data-ttu-id="d6481-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d6481-105">Method</span></span>|<span data-ttu-id="d6481-106">説明</span><span class="sxs-lookup"><span data-stu-id="d6481-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d6481-107">EnumerateTypeParameters メソッド</span><span class="sxs-lookup"><span data-stu-id="d6481-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="d6481-108">このフレームのパラメーターを格納している<xref:System.Type> 、テキスト型の型の列挙体オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="d6481-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="d6481-109">RemapFunction メソッド</span><span class="sxs-lookup"><span data-stu-id="d6481-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="d6481-110">新しい MSIL オフセットを指定して、編集された関数を再マップします。</span><span class="sxs-lookup"><span data-stu-id="d6481-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6481-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="d6481-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6481-112">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d6481-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6481-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="d6481-113">Requirements</span></span>  
 <span data-ttu-id="d6481-114">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6481-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6481-115">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="d6481-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6481-116">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="d6481-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6481-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6481-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6481-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6481-118">See also</span></span>

- [<span data-ttu-id="d6481-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d6481-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
