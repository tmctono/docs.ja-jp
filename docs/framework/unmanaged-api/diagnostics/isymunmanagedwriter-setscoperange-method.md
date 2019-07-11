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
ms.openlocfilehash: c13eb7ca16cdb7c70f3fef0dd4efcb9362cd3d87
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776581"
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="42628-102">ISymUnmanagedWriter::SetScopeRange メソッド</span><span class="sxs-lookup"><span data-stu-id="42628-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>
<span data-ttu-id="42628-103">指定した構文のスコープのオフセット範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="42628-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="42628-104">スコープは、新しい現在のスコープになり、スコープのスタックにプッシュされます。</span><span class="sxs-lookup"><span data-stu-id="42628-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="42628-105">スコープは、階層を形成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42628-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="42628-106">兄弟は、重複は許可されません。</span><span class="sxs-lookup"><span data-stu-id="42628-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42628-107">構文</span><span class="sxs-lookup"><span data-stu-id="42628-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42628-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42628-108">Parameters</span></span>  
 `scopeId`  
 <span data-ttu-id="42628-109">[in]スコープのスコープの識別子です。</span><span class="sxs-lookup"><span data-stu-id="42628-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="42628-110">[in]メソッドの先頭から構文のスコープ内の最初の命令のバイト単位のオフセット。</span><span class="sxs-lookup"><span data-stu-id="42628-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="42628-111">[in]メソッドの先頭から構文のスコープの最後の命令のバイト単位のオフセット。</span><span class="sxs-lookup"><span data-stu-id="42628-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42628-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="42628-112">Return Value</span></span>  
 <span data-ttu-id="42628-113">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="42628-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42628-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="42628-114">Remarks</span></span>  
 <span data-ttu-id="42628-115">[Isymunmanagedwriter::openscope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)で使用できる非透過スコープ識別子を返します`ISymUnmanagedWriter::SetScopeRange`スコープを定義するの開始位置と終了後にオフセットします。</span><span class="sxs-lookup"><span data-stu-id="42628-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="42628-116">この場合に渡したオフセット`ISymUnmanagedWriter::OpenScope`と[isymunmanagedwriter::closescope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md)は無視されます。</span><span class="sxs-lookup"><span data-stu-id="42628-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="42628-117">スコープ識別子は、現在のメソッドでは無効です。</span><span class="sxs-lookup"><span data-stu-id="42628-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42628-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="42628-118">Requirements</span></span>  
 <span data-ttu-id="42628-119">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="42628-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42628-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="42628-120">See also</span></span>

- [<span data-ttu-id="42628-121">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42628-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
