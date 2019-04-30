---
title: ISymUnmanagedWriter::OpenScope メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenScope
helpviewer_keywords:
- OpenScope method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::OpenScope method [.NET Framework debugging]
ms.assetid: dbea0644-3873-4329-90b8-624163e87467
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ea6ce91e0651e09fb908d8b8b35811349ac8845
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986038"
---
# <a name="isymunmanagedwriteropenscope-method"></a><span data-ttu-id="0b6a3-102">ISymUnmanagedWriter::OpenScope メソッド</span><span class="sxs-lookup"><span data-stu-id="0b6a3-102">ISymUnmanagedWriter::OpenScope Method</span></span>
<span data-ttu-id="0b6a3-103">現在のメソッドの構文の新しいスコープを開きます。</span><span class="sxs-lookup"><span data-stu-id="0b6a3-103">Opens a new lexical scope in the current method.</span></span> <span data-ttu-id="0b6a3-104">スコープは、新しい現在のスコープになり、スコープのスタックにプッシュされます。</span><span class="sxs-lookup"><span data-stu-id="0b6a3-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="0b6a3-105">スコープは、階層を形成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b6a3-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="0b6a3-106">兄弟は、重複は許可されません。</span><span class="sxs-lookup"><span data-stu-id="0b6a3-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b6a3-107">構文</span><span class="sxs-lookup"><span data-stu-id="0b6a3-107">Syntax</span></span>  
  
```  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b6a3-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0b6a3-108">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="0b6a3-109">[in]メソッドの先頭からのバイト単位での構文のスコープ内の最初の命令のオフセット。</span><span class="sxs-lookup"><span data-stu-id="0b6a3-109">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="0b6a3-110">[out]ポインターを`ULONG32`スコープ識別子を受け取る。</span><span class="sxs-lookup"><span data-stu-id="0b6a3-110">[out] A pointer to a `ULONG32` that receives the scope identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b6a3-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="0b6a3-111">Return Value</span></span>  
 <span data-ttu-id="0b6a3-112">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="0b6a3-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b6a3-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="0b6a3-113">Remarks</span></span>  
 <span data-ttu-id="0b6a3-114">`ISymUnmanagedWriter::OpenScope` 使用できる非透過スコープ識別子を返します[isymunmanagedwriter::setscoperange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md)スコープを定義するの開始位置と終了後にオフセットします。</span><span class="sxs-lookup"><span data-stu-id="0b6a3-114">`ISymUnmanagedWriter::OpenScope` returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="0b6a3-115">この場合に渡したオフセット`ISymUnmanagedWriter::OpenScope`と[isymunmanagedwriter::closescope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md)は無視されます。</span><span class="sxs-lookup"><span data-stu-id="0b6a3-115">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="0b6a3-116">スコープ識別子は、現在のメソッドでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="0b6a3-116">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b6a3-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="0b6a3-117">Requirements</span></span>  
 <span data-ttu-id="0b6a3-118">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0b6a3-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b6a3-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b6a3-119">See also</span></span>

- [<span data-ttu-id="0b6a3-120">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0b6a3-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
