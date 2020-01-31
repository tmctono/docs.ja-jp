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
ms.openlocfilehash: c5fa0a67309e23c02393b70d849af3884dfd0adf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788540"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="1416c-102">ICorDebugILFrame2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1416c-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="1416c-103">モジュールの論理拡張機能インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="1416c-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1416c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="1416c-104">Methods</span></span>  
  
|<span data-ttu-id="1416c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1416c-105">Method</span></span>|<span data-ttu-id="1416c-106">説明</span><span class="sxs-lookup"><span data-stu-id="1416c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1416c-107">EnumerateTypeParameters メソッド</span><span class="sxs-lookup"><span data-stu-id="1416c-107">EnumerateTypeParameters Method</span></span>](icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="1416c-108">このフレームの <xref:System.Type> パラメーターを格納している、テキスト型オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="1416c-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="1416c-109">RemapFunction メソッド</span><span class="sxs-lookup"><span data-stu-id="1416c-109">RemapFunction Method</span></span>](icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="1416c-110">新しい MSIL オフセットを指定して、編集された関数を再マップします。</span><span class="sxs-lookup"><span data-stu-id="1416c-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1416c-111">コメント</span><span class="sxs-lookup"><span data-stu-id="1416c-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1416c-112">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1416c-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1416c-113">要件</span><span class="sxs-lookup"><span data-stu-id="1416c-113">Requirements</span></span>  
 <span data-ttu-id="1416c-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1416c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1416c-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1416c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1416c-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1416c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1416c-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1416c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1416c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="1416c-118">See also</span></span>

- [<span data-ttu-id="1416c-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1416c-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
