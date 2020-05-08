---
title: ICorDebugExceptionObjectValue インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue
helpviewer_keywords:
- ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type:
- apiref
ms.openlocfilehash: 8e4f745440936a39e22faf60d10a05a0bb110606
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975954"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="c5612-102">ICorDebugExceptionObjectValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c5612-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="c5612-103">"は、マネージ例外オブジェクトからスタックトレース情報を提供するために、" は、"" のような "のインターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="c5612-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c5612-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="c5612-104">Methods</span></span>  
  
|<span data-ttu-id="c5612-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="c5612-105">Method</span></span>|<span data-ttu-id="c5612-106">説明</span><span class="sxs-lookup"><span data-stu-id="c5612-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c5612-107">EnumerateExceptionCallStack メソッド</span><span class="sxs-lookup"><span data-stu-id="c5612-107">EnumerateExceptionCallStack Method</span></span>](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="c5612-108">例外オブジェクトに埋め込まれている呼び出し履歴に対する列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="c5612-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5612-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="c5612-109">Remarks</span></span>  
 <span data-ttu-id="c5612-110">の呼び出し`QueryInterface`は、から<xref:System.Exception?displayProperty=nameWithType>派生したマネージオブジェクトに対して成功します。</span><span class="sxs-lookup"><span data-stu-id="c5612-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5612-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="c5612-111">Requirements</span></span>  
 <span data-ttu-id="c5612-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5612-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5612-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5612-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5612-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5612-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5612-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5612-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5612-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5612-116">See also</span></span>

- [<span data-ttu-id="c5612-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="c5612-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c5612-118">デバッグ</span><span class="sxs-lookup"><span data-stu-id="c5612-118">Debugging</span></span>](index.md)
