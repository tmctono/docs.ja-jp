---
title: ISymUnmanagedWriter::DefineLocalVariable メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineLocalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type:
- apiref
ms.openlocfilehash: f6a741df3ea57b5e9b4fa8bc5d304bfedd1d6c15
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428012"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="a6fee-102">ISymUnmanagedWriter::DefineLocalVariable メソッド</span><span class="sxs-lookup"><span data-stu-id="a6fee-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="a6fee-103">現在の構文のスコープの変数を 1 つ定義します。</span><span class="sxs-lookup"><span data-stu-id="a6fee-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="a6fee-104">このメソッドは、スコープ全体で複数のホームを持つ同じ名前の変数に対して複数回呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a6fee-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="a6fee-105">ただし、この場合、`startOffset` パラメーターと `endOffset` パラメーターの値は重複してはなりません。</span><span class="sxs-lookup"><span data-stu-id="a6fee-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6fee-106">構文</span><span class="sxs-lookup"><span data-stu-id="a6fee-106">Syntax</span></span>  
  
```cpp  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6fee-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a6fee-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="a6fee-108">からローカル変数名を定義する `WCHAR` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a6fee-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="a6fee-109">からローカル変数の属性。</span><span class="sxs-lookup"><span data-stu-id="a6fee-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="a6fee-110">から`signature` バッファーのサイズ (バイト単位) を示す `ULONG32`。</span><span class="sxs-lookup"><span data-stu-id="a6fee-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="a6fee-111">からローカル変数シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="a6fee-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="a6fee-112">からアドレスの種類。</span><span class="sxs-lookup"><span data-stu-id="a6fee-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="a6fee-113">からパラメーター指定の最初のアドレス。</span><span class="sxs-lookup"><span data-stu-id="a6fee-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="a6fee-114">からパラメーター指定の2番目のアドレス。</span><span class="sxs-lookup"><span data-stu-id="a6fee-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="a6fee-115">からパラメーター指定の3番目のアドレス。</span><span class="sxs-lookup"><span data-stu-id="a6fee-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="a6fee-116">から変数の開始オフセット。</span><span class="sxs-lookup"><span data-stu-id="a6fee-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="a6fee-117">このパラメーターはオプションです。</span><span class="sxs-lookup"><span data-stu-id="a6fee-117">This parameter is optional.</span></span> <span data-ttu-id="a6fee-118">0の場合、このパラメーターは無視され、スコープ全体にわたって変数が定義されます。</span><span class="sxs-lookup"><span data-stu-id="a6fee-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="a6fee-119">0以外の値の場合、変数は現在のスコープのオフセット内になります。</span><span class="sxs-lookup"><span data-stu-id="a6fee-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="a6fee-120">から変数の終了オフセット。</span><span class="sxs-lookup"><span data-stu-id="a6fee-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="a6fee-121">このパラメーターはオプションです。</span><span class="sxs-lookup"><span data-stu-id="a6fee-121">This parameter is optional.</span></span> <span data-ttu-id="a6fee-122">0の場合、このパラメーターは無視され、スコープ全体にわたって変数が定義されます。</span><span class="sxs-lookup"><span data-stu-id="a6fee-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="a6fee-123">0以外の値の場合、変数は現在のスコープのオフセット内になります。</span><span class="sxs-lookup"><span data-stu-id="a6fee-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6fee-124">戻り値</span><span class="sxs-lookup"><span data-stu-id="a6fee-124">Return Value</span></span>  
 <span data-ttu-id="a6fee-125">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="a6fee-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6fee-126">要件</span><span class="sxs-lookup"><span data-stu-id="a6fee-126">Requirements</span></span>  
 <span data-ttu-id="a6fee-127">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="a6fee-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6fee-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6fee-128">See also</span></span>

- [<span data-ttu-id="a6fee-129">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6fee-129">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="a6fee-130">DefineGlobalVariable メソッド</span><span class="sxs-lookup"><span data-stu-id="a6fee-130">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
- [<span data-ttu-id="a6fee-131">DefineLocalVariable2 メソッド</span><span class="sxs-lookup"><span data-stu-id="a6fee-131">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)
