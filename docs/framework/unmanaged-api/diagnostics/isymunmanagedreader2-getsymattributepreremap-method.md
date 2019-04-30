---
title: ISymUnmanagedReader2::GetSymAttributePreRemap メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetSymAttributePreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 543a8015e944333942b619060059273577902a74
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986337"
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a><span data-ttu-id="eaa23-102">ISymUnmanagedReader2::GetSymAttributePreRemap メソッド</span><span class="sxs-lookup"><span data-stu-id="eaa23-102">ISymUnmanagedReader2::GetSymAttributePreRemap Method</span></span>
<span data-ttu-id="eaa23-103">その名前に基づくカスタム属性を取得します。</span><span class="sxs-lookup"><span data-stu-id="eaa23-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="eaa23-104">メタデータのカスタム属性とは異なり、これらの属性は、シンボル ストアに保持されます。</span><span class="sxs-lookup"><span data-stu-id="eaa23-104">Unlike metadata custom attributes, these attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaa23-105">構文</span><span class="sxs-lookup"><span data-stu-id="eaa23-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eaa23-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eaa23-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="eaa23-107">[in]親のメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="eaa23-107">[in] The metadata token of the parent.</span></span>  
  
 `name`  
 <span data-ttu-id="eaa23-108">[in]ポインターを`WCHAR`名前を格納します。</span><span class="sxs-lookup"><span data-stu-id="eaa23-108">[in] A pointer to a `WCHAR` that contains the name.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="eaa23-109">[in]A`ULONG32`のサイズを示す、`buffer`配列。</span><span class="sxs-lookup"><span data-stu-id="eaa23-109">[in] A `ULONG32` that indicates the size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="eaa23-110">[out]ポインターを`ULONG32`属性データの格納に必要なバッファーのサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="eaa23-110">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the attribute bytes.</span></span>  
  
 `buffer`  
 <span data-ttu-id="eaa23-111">[out]属性のバイトを受け取るバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="eaa23-111">[out] A pointer to the buffer that receives the attribute bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eaa23-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="eaa23-112">Return Value</span></span>  
 <span data-ttu-id="eaa23-113">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="eaa23-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaa23-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="eaa23-114">Requirements</span></span>  
 <span data-ttu-id="eaa23-115">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="eaa23-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaa23-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="eaa23-116">See also</span></span>

- [<span data-ttu-id="eaa23-117">ISymUnmanagedReader2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eaa23-117">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
