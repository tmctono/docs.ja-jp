---
title: ISymUnmanagedWriter::CloseScope メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
ms.openlocfilehash: 264b4487483ed5439a9809feefcdc1b20af402dc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428078"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="d7d69-102">ISymUnmanagedWriter::CloseScope メソッド</span><span class="sxs-lookup"><span data-stu-id="d7d69-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="d7d69-103">現在の構文のスコープを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d7d69-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7d69-104">構文</span><span class="sxs-lookup"><span data-stu-id="d7d69-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7d69-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d7d69-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="d7d69-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span><span class="sxs-lookup"><span data-stu-id="d7d69-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7d69-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="d7d69-107">Return Value</span></span>  
 <span data-ttu-id="d7d69-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="d7d69-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7d69-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="d7d69-109">Remarks</span></span>  
 <span data-ttu-id="d7d69-110">Once a scope is closed, no more variables can be defined within it.</span><span class="sxs-lookup"><span data-stu-id="d7d69-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="d7d69-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span><span class="sxs-lookup"><span data-stu-id="d7d69-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="d7d69-112">この場合、`ISymUnmanagedWriter::OpenScope` と `ISymUnmanagedWriter::CloseScope` に渡したオフセットは無視されます。</span><span class="sxs-lookup"><span data-stu-id="d7d69-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="d7d69-113">Scope identifiers are valid only in the current method.</span><span class="sxs-lookup"><span data-stu-id="d7d69-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7d69-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="d7d69-114">Requirements</span></span>  
 <span data-ttu-id="d7d69-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d7d69-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7d69-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7d69-116">See also</span></span>

- [<span data-ttu-id="d7d69-117">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7d69-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
