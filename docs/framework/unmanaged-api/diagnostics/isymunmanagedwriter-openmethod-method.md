---
title: ISymUnmanagedWriter::OpenMethod メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type:
- apiref
ms.openlocfilehash: 7b13ca9884516e95e0bb922efc5bc1a845344e38
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427918"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="bbeb7-102">ISymUnmanagedWriter::OpenMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="bbeb7-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="bbeb7-103">Opens a method into which symbol information is emitted.</span><span class="sxs-lookup"><span data-stu-id="bbeb7-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="bbeb7-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span><span class="sxs-lookup"><span data-stu-id="bbeb7-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="bbeb7-105">There is an implicit lexical scope around the entire method.</span><span class="sxs-lookup"><span data-stu-id="bbeb7-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="bbeb7-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span><span class="sxs-lookup"><span data-stu-id="bbeb7-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="bbeb7-107">There can be only one open method at a time.</span><span class="sxs-lookup"><span data-stu-id="bbeb7-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbeb7-108">構文</span><span class="sxs-lookup"><span data-stu-id="bbeb7-108">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbeb7-109">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bbeb7-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="bbeb7-110">[in] The metadata token for the method to be opened.</span><span class="sxs-lookup"><span data-stu-id="bbeb7-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bbeb7-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="bbeb7-111">Return Value</span></span>  
 <span data-ttu-id="bbeb7-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="bbeb7-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbeb7-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="bbeb7-113">Requirements</span></span>  
 <span data-ttu-id="bbeb7-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bbeb7-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbeb7-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="bbeb7-115">See also</span></span>

- [<span data-ttu-id="bbeb7-116">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bbeb7-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="bbeb7-117">CloseMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="bbeb7-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="bbeb7-118">OpenMethod2 メソッド</span><span class="sxs-lookup"><span data-stu-id="bbeb7-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
