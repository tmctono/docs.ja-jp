---
title: ISymUnmanagedDocumentWriter::SetSource メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetSource
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetSource method [.NET Framework debugging]
- SetSource method [.NET Framework debugging]
ms.assetid: ea5b9d9f-ff06-4bd3-8de5-6435343aba59
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 555926e0e6a669f70bdeff484cff0eb62ae11f7b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776943"
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="f6640-102">ISymUnmanagedDocumentWriter::SetSource メソッド</span><span class="sxs-lookup"><span data-stu-id="f6640-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>
<span data-ttu-id="f6640-103">セットには、書き込まれるドキュメントのソースが埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="f6640-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6640-104">構文</span><span class="sxs-lookup"><span data-stu-id="f6640-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6640-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f6640-105">Parameters</span></span>  
 `sourceSize`  
 <span data-ttu-id="f6640-106">[in]A`ULONG32`のサイズを格納している、`source`バッファー。</span><span class="sxs-lookup"><span data-stu-id="f6640-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="f6640-107">[in]埋め込みのソースを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="f6640-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6640-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="f6640-108">Return Value</span></span>  
 <span data-ttu-id="f6640-109">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="f6640-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6640-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="f6640-110">Requirements</span></span>  
 <span data-ttu-id="f6640-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f6640-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6640-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6640-112">See also</span></span>

- [<span data-ttu-id="f6640-113">ISymUnmanagedDocumentWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f6640-113">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
