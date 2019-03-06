---
title: ISymUnmanagedReader2::GetMethodsInDocument メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodsInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument
helpviewer_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument method [.NET Framework debugging]
- GetMethodsInDocument method [.NET Framework debugging]
ms.assetid: c7ae84d6-81e8-4cb7-a1f9-d48b6cde5d79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 26e6efff403f7fa10e1d96ffb3bf0f4b9ab3a96d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465856"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a><span data-ttu-id="911bc-102">ISymUnmanagedReader2::GetMethodsInDocument メソッド</span><span class="sxs-lookup"><span data-stu-id="911bc-102">ISymUnmanagedReader2::GetMethodsInDocument Method</span></span>
<span data-ttu-id="911bc-103">指定されたドキュメント内の行情報を持つすべてのメソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="911bc-103">Gets every method that has line information in the provided document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="911bc-104">構文</span><span class="sxs-lookup"><span data-stu-id="911bc-104">Syntax</span></span>  
  
```  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="911bc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="911bc-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="911bc-106">[in]ドキュメントへのポインター。</span><span class="sxs-lookup"><span data-stu-id="911bc-106">[in] A pointer to the document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="911bc-107">[in]A`ULONG32`のサイズを示す、`pRetVal`配列。</span><span class="sxs-lookup"><span data-stu-id="911bc-107">[in] A `ULONG32` that indicates the size of the  `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="911bc-108">[out]ポインターを`ULONG32`メソッドの格納に必要なバッファーのサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="911bc-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the methods.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="911bc-109">[out]メソッドが受け取るバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="911bc-109">[out] A pointer to the buffer that receives the methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="911bc-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="911bc-110">Return Value</span></span>  
 <span data-ttu-id="911bc-111">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="911bc-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="911bc-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="911bc-112">Requirements</span></span>  
 <span data-ttu-id="911bc-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="911bc-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="911bc-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="911bc-114">See also</span></span>
- [<span data-ttu-id="911bc-115">ISymUnmanagedReader2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="911bc-115">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
