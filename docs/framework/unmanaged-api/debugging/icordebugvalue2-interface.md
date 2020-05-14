---
title: ICorDebugValue2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
ms.openlocfilehash: d036ddf353aa3a622ade05e1e2daa7f170d28f63
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396777"
---
# <a name="icordebugvalue2-interface"></a><span data-ttu-id="a8f1c-102">ICorDebugValue2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a8f1c-102">ICorDebugValue2 Interface</span></span>
<span data-ttu-id="a8f1c-103">"ICorDebugValue" インターフェイスを拡張して "テキスト" オブジェクトのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="a8f1c-103">Extends the "ICorDebugValue" interface to provide support for "ICorDebugType" objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8f1c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="a8f1c-104">Methods</span></span>  
  
|<span data-ttu-id="a8f1c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a8f1c-105">Method</span></span>|<span data-ttu-id="a8f1c-106">説明</span><span class="sxs-lookup"><span data-stu-id="a8f1c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8f1c-107">GetExactType メソッド</span><span class="sxs-lookup"><span data-stu-id="a8f1c-107">GetExactType Method</span></span>](icordebugvalue2-getexacttype-method.md)|<span data-ttu-id="a8f1c-108">この値のを表すオブジェクトへのインターフェイスポインターを取得し `ICorDebugType` <xref:System.Type> ます。</span><span class="sxs-lookup"><span data-stu-id="a8f1c-108">Gets an interface pointer to an `ICorDebugType` object that represents the <xref:System.Type> of this value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8f1c-109">解説</span><span class="sxs-lookup"><span data-stu-id="a8f1c-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a8f1c-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a8f1c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8f1c-111">要件</span><span class="sxs-lookup"><span data-stu-id="a8f1c-111">Requirements</span></span>  
 <span data-ttu-id="a8f1c-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8f1c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8f1c-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8f1c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8f1c-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8f1c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8f1c-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8f1c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8f1c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8f1c-116">See also</span></span>

- [<span data-ttu-id="a8f1c-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="a8f1c-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

- [<span data-ttu-id="a8f1c-118">ICorDebugValue3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a8f1c-118">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
