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
ms.openlocfilehash: 4450c262b75a73114cb7de7de98567f053bbf564
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894470"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="cafb6-102">ISymUnmanagedWriter::SetSymAttribute メソッド</span><span class="sxs-lookup"><span data-stu-id="cafb6-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="cafb6-103">名前に基づいてカスタム属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="cafb6-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="cafb6-104">これらの属性は、メタデータのカスタム属性とは異なり、シンボルストアに保持されます。</span><span class="sxs-lookup"><span data-stu-id="cafb6-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cafb6-105">構文</span><span class="sxs-lookup"><span data-stu-id="cafb6-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cafb6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cafb6-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="cafb6-107">から属性を定義するメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="cafb6-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="cafb6-108">から属性名を格納`WCHAR`しているへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cafb6-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="cafb6-109">から配列の`data`サイズを示す。 `ULONG32`</span><span class="sxs-lookup"><span data-stu-id="cafb6-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="cafb6-110">から属性値。</span><span class="sxs-lookup"><span data-stu-id="cafb6-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cafb6-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="cafb6-111">Return Value</span></span>  
 <span data-ttu-id="cafb6-112">メソッドが成功した場合は S_OK を返します。それ以外の場合は E_FAIL またはその他のエラーコードを返します。</span><span class="sxs-lookup"><span data-stu-id="cafb6-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cafb6-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="cafb6-113">Requirements</span></span>  
 <span data-ttu-id="cafb6-114">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="cafb6-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cafb6-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="cafb6-115">See also</span></span>

- [<span data-ttu-id="cafb6-116">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cafb6-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
