---
title: ISymUnmanagedBinder::GetReaderFromStream メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderFromStream
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 21e147860c6859ea23409de31fed972c4f2bb432
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220917"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="6530d-102">ISymUnmanagedBinder::GetReaderFromStream メソッド</span><span class="sxs-lookup"><span data-stu-id="6530d-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="6530d-103">メタデータ インターフェイスとシンボル ストアを格納しているストリームでは、指定されたを返します、正しい[ISymUnmanagedReader](isymunmanagedreader-interface.md)構造は、デバッグを読み取ることが特定のシンボル ストアからシンボルします。</span><span class="sxs-lookup"><span data-stu-id="6530d-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6530d-104">構文</span><span class="sxs-lookup"><span data-stu-id="6530d-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6530d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6530d-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="6530d-106">[in]メタデータ インポート インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6530d-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="6530d-107">[in]シンボル ストアを格納しているストリームへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6530d-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="6530d-108">[out]設定されているポインターに返された[ISymUnmanagedReader](isymunmanagedreader-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6530d-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6530d-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="6530d-109">Return Value</span></span>  
 <span data-ttu-id="6530d-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="6530d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6530d-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="6530d-111">Requirements</span></span>  
 <span data-ttu-id="6530d-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6530d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6530d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="6530d-113">See also</span></span>

- [<span data-ttu-id="6530d-114">ISymUnmanagedBinder インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6530d-114">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
