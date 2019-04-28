---
title: ISymUnmanagedWriter::SetSymAttribute メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8ffcc3a079e7e9a9d69622dc6666bb0e7641d4e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650779"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="e475d-102">ISymUnmanagedWriter::SetSymAttribute メソッド</span><span class="sxs-lookup"><span data-stu-id="e475d-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="e475d-103">その名前に基づくカスタム属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="e475d-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="e475d-104">これらの属性は、カスタム属性のメタデータとは異なり、シンボル ストアに保持されます。</span><span class="sxs-lookup"><span data-stu-id="e475d-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e475d-105">構文</span><span class="sxs-lookup"><span data-stu-id="e475d-105">Syntax</span></span>  
  
```  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e475d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e475d-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="e475d-107">[in]属性を定義するメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="e475d-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="e475d-108">[in]ポインターを`WCHAR`属性名を格納しています。</span><span class="sxs-lookup"><span data-stu-id="e475d-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="e475d-109">[in]A`ULONG32`のサイズを示す、`data`配列。</span><span class="sxs-lookup"><span data-stu-id="e475d-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="e475d-110">[in]属性の値。</span><span class="sxs-lookup"><span data-stu-id="e475d-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e475d-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="e475d-111">Return Value</span></span>  
 <span data-ttu-id="e475d-112">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="e475d-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e475d-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="e475d-113">Requirements</span></span>  
 <span data-ttu-id="e475d-114">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e475d-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e475d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e475d-115">See also</span></span>

- [<span data-ttu-id="e475d-116">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e475d-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
