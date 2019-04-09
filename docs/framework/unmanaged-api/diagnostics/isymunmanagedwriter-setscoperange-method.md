---
title: ISymUnmanagedWriter::SetScopeRange メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetScopeRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetScopeRange
helpviewer_keywords:
- SetScopeRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetScopeRange method [.NET Framework debugging]
ms.assetid: d4d98676-444b-46ca-bfe6-0d827385cd22
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d7fe8f36c7a5dbe6e715402fd7253092b64e68e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078968"
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="f023d-102">ISymUnmanagedWriter::SetScopeRange メソッド</span><span class="sxs-lookup"><span data-stu-id="f023d-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>
<span data-ttu-id="f023d-103">指定した構文のスコープのオフセット範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="f023d-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="f023d-104">スコープは、新しい現在のスコープになり、スコープのスタックにプッシュされます。</span><span class="sxs-lookup"><span data-stu-id="f023d-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="f023d-105">スコープは、階層を形成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f023d-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="f023d-106">兄弟は、重複は許可されません。</span><span class="sxs-lookup"><span data-stu-id="f023d-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f023d-107">構文</span><span class="sxs-lookup"><span data-stu-id="f023d-107">Syntax</span></span>  
  
```  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f023d-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f023d-108">Parameters</span></span>  
 `scopeId`  
 <span data-ttu-id="f023d-109">[in]スコープのスコープの識別子です。</span><span class="sxs-lookup"><span data-stu-id="f023d-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="f023d-110">[in]メソッドの先頭から構文のスコープ内の最初の命令のバイト単位のオフセット。</span><span class="sxs-lookup"><span data-stu-id="f023d-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="f023d-111">[in]メソッドの先頭から構文のスコープの最後の命令のバイト単位のオフセット。</span><span class="sxs-lookup"><span data-stu-id="f023d-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f023d-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="f023d-112">Return Value</span></span>  
 <span data-ttu-id="f023d-113">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="f023d-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f023d-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="f023d-114">Remarks</span></span>  
 <span data-ttu-id="f023d-115">[Isymunmanagedwriter::openscope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)で使用できる非透過スコープ識別子を返します`ISymUnmanagedWriter::SetScopeRange`スコープを定義するの開始位置と終了後にオフセットします。</span><span class="sxs-lookup"><span data-stu-id="f023d-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="f023d-116">この場合に渡したオフセット`ISymUnmanagedWriter::OpenScope`と[isymunmanagedwriter::closescope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md)は無視されます。</span><span class="sxs-lookup"><span data-stu-id="f023d-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="f023d-117">スコープ識別子は、現在のメソッドでは無効です。</span><span class="sxs-lookup"><span data-stu-id="f023d-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f023d-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="f023d-118">Requirements</span></span>  
 <span data-ttu-id="f023d-119">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f023d-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f023d-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f023d-120">See also</span></span>

- [<span data-ttu-id="f023d-121">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f023d-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
