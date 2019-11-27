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
ms.openlocfilehash: ff18f95bd6b4cfde5aaa4d3f6f68b58fd37c04b3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449071"
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="3bc3d-102">ISymUnmanagedDocumentWriter::SetSource メソッド</span><span class="sxs-lookup"><span data-stu-id="3bc3d-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>
<span data-ttu-id="3bc3d-103">書き込まれるドキュメントの埋め込み元を設定します。</span><span class="sxs-lookup"><span data-stu-id="3bc3d-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bc3d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3bc3d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bc3d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3bc3d-105">Parameters</span></span>  
 `sourceSize`  
 <span data-ttu-id="3bc3d-106">から`source` バッファーのサイズを格納している `ULONG32`。</span><span class="sxs-lookup"><span data-stu-id="3bc3d-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="3bc3d-107">から埋め込みソースを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="3bc3d-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3bc3d-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="3bc3d-108">Return Value</span></span>  
 <span data-ttu-id="3bc3d-109">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="3bc3d-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bc3d-110">要件</span><span class="sxs-lookup"><span data-stu-id="3bc3d-110">Requirements</span></span>  
 <span data-ttu-id="3bc3d-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="3bc3d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bc3d-112">参照</span><span class="sxs-lookup"><span data-stu-id="3bc3d-112">See also</span></span>

- [<span data-ttu-id="3bc3d-113">ISymUnmanagedDocumentWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3bc3d-113">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
