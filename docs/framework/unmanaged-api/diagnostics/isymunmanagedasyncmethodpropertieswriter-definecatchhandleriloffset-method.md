---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset メソッド
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
ms.openlocfilehash: b108c8c87d3afdbfacb569ab501274e5c45c2e2e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129185"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="61f6d-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="61f6d-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="61f6d-103">非同期メソッドをラップする、コンパイラによって生成される catch ハンドラーの IL オフセットを設定します。</span><span class="sxs-lookup"><span data-stu-id="61f6d-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="61f6d-104">生成された catch の IL オフセットは、ユーザーコードメソッドで発生する可能性があっても、ユーザーコード以外のコードであると仮定して、catch を処理するためにデバッガーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="61f6d-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="61f6d-105">特に、 **CatchHandlerFound** exception イベントに応答して使用されます。</span><span class="sxs-lookup"><span data-stu-id="61f6d-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61f6d-106">構文</span><span class="sxs-lookup"><span data-stu-id="61f6d-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61f6d-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="61f6d-107">Parameters</span></span>  
  
|<span data-ttu-id="61f6d-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="61f6d-108">Parameter</span></span>|<span data-ttu-id="61f6d-109">説明</span><span class="sxs-lookup"><span data-stu-id="61f6d-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="61f6d-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="61f6d-110">Return Value</span></span>  
 <span data-ttu-id="61f6d-111">`HRESULT`を返します。</span><span class="sxs-lookup"><span data-stu-id="61f6d-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61f6d-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="61f6d-112">Requirements</span></span>  
 <span data-ttu-id="61f6d-113">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="61f6d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61f6d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="61f6d-114">See also</span></span>

- [<span data-ttu-id="61f6d-115">ISymUnmanagedAsyncMethodPropertiesWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61f6d-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
