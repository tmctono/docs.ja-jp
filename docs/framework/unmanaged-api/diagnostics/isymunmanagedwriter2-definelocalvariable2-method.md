---
title: ISymUnmanagedWriter2::DefineLocalVariable2 メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
ms.openlocfilehash: ac7559bd5431f45b266602404ddde9081aa2944d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614696"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="628b8-102">ISymUnmanagedWriter2::DefineLocalVariable2 メソッド</span><span class="sxs-lookup"><span data-stu-id="628b8-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>
<span data-ttu-id="628b8-103">現在の構文のスコープの変数を 1 つ定義します。</span><span class="sxs-lookup"><span data-stu-id="628b8-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="628b8-104">このメソッドは、スコープ全体で複数のホームを持つ同じ名前の変数に対して複数回呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="628b8-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="628b8-105">ただし、この場合は、 `startOffset` パラメーターとパラメーターの値 `endOffset` が重複していてはなりません。</span><span class="sxs-lookup"><span data-stu-id="628b8-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="628b8-106">構文</span><span class="sxs-lookup"><span data-stu-id="628b8-106">Syntax</span></span>  
  
```cpp  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="628b8-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="628b8-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="628b8-108">からローカル変数名。</span><span class="sxs-lookup"><span data-stu-id="628b8-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="628b8-109">からローカル変数の属性。</span><span class="sxs-lookup"><span data-stu-id="628b8-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="628b8-110">から署名のメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="628b8-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="628b8-111">からアドレスの種類。</span><span class="sxs-lookup"><span data-stu-id="628b8-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="628b8-112">からパラメーター指定の最初のアドレス。</span><span class="sxs-lookup"><span data-stu-id="628b8-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="628b8-113">からパラメーター指定の2番目のアドレス。</span><span class="sxs-lookup"><span data-stu-id="628b8-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="628b8-114">からパラメーター指定の3番目のアドレス。</span><span class="sxs-lookup"><span data-stu-id="628b8-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="628b8-115">から変数の開始オフセット。</span><span class="sxs-lookup"><span data-stu-id="628b8-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="628b8-116">このパラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="628b8-116">This parameter is optional.</span></span> <span data-ttu-id="628b8-117">0の場合、このパラメーターは無視され、スコープ全体にわたって変数が定義されます。</span><span class="sxs-lookup"><span data-stu-id="628b8-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="628b8-118">0以外の値の場合、変数は現在のスコープのオフセット内になります。</span><span class="sxs-lookup"><span data-stu-id="628b8-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="628b8-119">から変数の終了オフセット。</span><span class="sxs-lookup"><span data-stu-id="628b8-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="628b8-120">このパラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="628b8-120">This parameter is optional.</span></span> <span data-ttu-id="628b8-121">0の場合、このパラメーターは無視され、スコープ全体にわたって変数が定義されます。</span><span class="sxs-lookup"><span data-stu-id="628b8-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="628b8-122">0以外の値の場合、変数は現在のスコープのオフセット内になります。</span><span class="sxs-lookup"><span data-stu-id="628b8-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="628b8-123">戻り値</span><span class="sxs-lookup"><span data-stu-id="628b8-123">Return Value</span></span>  
 <span data-ttu-id="628b8-124">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="628b8-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="628b8-125">要件</span><span class="sxs-lookup"><span data-stu-id="628b8-125">Requirements</span></span>  
 <span data-ttu-id="628b8-126">**ヘッダー:** CorSym .idl</span><span class="sxs-lookup"><span data-stu-id="628b8-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="628b8-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="628b8-127">See also</span></span>

- [<span data-ttu-id="628b8-128">ISymUnmanagedWriter2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="628b8-128">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="628b8-129">DefineLocalVariable メソッド</span><span class="sxs-lookup"><span data-stu-id="628b8-129">DefineLocalVariable Method</span></span>](isymunmanagedwriter-definelocalvariable-method.md)
