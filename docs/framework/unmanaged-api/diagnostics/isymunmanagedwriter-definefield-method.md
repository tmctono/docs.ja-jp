---
title: ISymUnmanagedWriter::DefineField メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineField
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 37794d40b4b379c5d3a05935cf1f2b7b3da11baa
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777370"
---
# <a name="isymunmanagedwriterdefinefield-method"></a><span data-ttu-id="539fd-102">ISymUnmanagedWriter::DefineField メソッド</span><span class="sxs-lookup"><span data-stu-id="539fd-102">ISymUnmanagedWriter::DefineField Method</span></span>
<span data-ttu-id="539fd-103">メソッド内ではない 1 つの変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="539fd-103">Defines a single variable that is not within a method.</span></span> <span data-ttu-id="539fd-104">このメソッドは、使用のクラス内の特定のフィールド、ビット フィールド、および具合です。</span><span class="sxs-lookup"><span data-stu-id="539fd-104">This method is used for certain fields in classes, bit fields, and so on.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="539fd-105">構文</span><span class="sxs-lookup"><span data-stu-id="539fd-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="539fd-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="539fd-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="539fd-107">[in]メタデータ型またはメソッド トークン。</span><span class="sxs-lookup"><span data-stu-id="539fd-107">[in] The metadata type or method token.</span></span>  
  
 `name`  
 <span data-ttu-id="539fd-108">[in]フィールド名です。</span><span class="sxs-lookup"><span data-stu-id="539fd-108">[in] The field name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="539fd-109">[in]フィールドの属性。</span><span class="sxs-lookup"><span data-stu-id="539fd-109">[in] The field attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="539fd-110">[in]A`ULONG32`文字のフィールドのシグネチャを格納するために必要なバッファーのサイズはします。</span><span class="sxs-lookup"><span data-stu-id="539fd-110">[in] A `ULONG32` that is the size, in characters, of the buffer required to contain the field signature.</span></span>  
  
 `signature`  
 <span data-ttu-id="539fd-111">[in]フィールドの署名の配列。</span><span class="sxs-lookup"><span data-stu-id="539fd-111">[in] The array of field signatures.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="539fd-112">[in]アドレスの種類。</span><span class="sxs-lookup"><span data-stu-id="539fd-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="539fd-113">[in]フィールド指定の最初のアドレス。</span><span class="sxs-lookup"><span data-stu-id="539fd-113">[in] The first address for the field specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="539fd-114">[in]フィールド指定の 2 番目のアドレス。</span><span class="sxs-lookup"><span data-stu-id="539fd-114">[in] The second address for the field specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="539fd-115">[in]フィールド指定の 3 番目のアドレス。</span><span class="sxs-lookup"><span data-stu-id="539fd-115">[in] The third address for the field specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="539fd-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="539fd-116">Return Value</span></span>  
 <span data-ttu-id="539fd-117">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="539fd-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="539fd-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="539fd-118">Requirements</span></span>  
 <span data-ttu-id="539fd-119">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="539fd-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="539fd-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="539fd-120">See also</span></span>

- [<span data-ttu-id="539fd-121">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="539fd-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
