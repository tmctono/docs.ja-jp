---
title: ISymUnmanagedReader::GetDocuments メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocuments
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocuments
helpviewer_keywords:
- GetDocuments method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocuments method [.NET Framework debugging]
ms.assetid: e3b73a3f-d089-4101-a9a9-5e0765d05b61
topic_type:
- apiref
ms.openlocfilehash: c26c0a5f8c597613266e2e6d1998edfca8f17b82
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448329"
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="8d3a5-102">ISymUnmanagedReader::GetDocuments メソッド</span><span class="sxs-lookup"><span data-stu-id="8d3a5-102">ISymUnmanagedReader::GetDocuments Method</span></span>
<span data-ttu-id="8d3a5-103">シンボルストアに定義されているすべてのドキュメントの配列を返します。</span><span class="sxs-lookup"><span data-stu-id="8d3a5-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d3a5-104">構文</span><span class="sxs-lookup"><span data-stu-id="8d3a5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d3a5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8d3a5-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="8d3a5-106">[in] `pDocs` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="8d3a5-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="8d3a5-107">入出力配列長を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8d3a5-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="8d3a5-108">入出力ドキュメント配列を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8d3a5-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d3a5-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="8d3a5-109">Return Value</span></span>  
 <span data-ttu-id="8d3a5-110">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="8d3a5-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d3a5-111">要件</span><span class="sxs-lookup"><span data-stu-id="8d3a5-111">Requirements</span></span>  
 <span data-ttu-id="8d3a5-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="8d3a5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d3a5-113">参照</span><span class="sxs-lookup"><span data-stu-id="8d3a5-113">See also</span></span>

- [<span data-ttu-id="8d3a5-114">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8d3a5-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
