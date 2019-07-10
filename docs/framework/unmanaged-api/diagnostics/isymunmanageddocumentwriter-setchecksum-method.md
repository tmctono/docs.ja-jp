---
title: ISymUnmanagedDocumentWriter::SetCheckSum メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum method [.NET Framework debugging]
- SetCheckSum method [.NET Framework debugging]
ms.assetid: c7e99879-421f-43ce-b193-34733cf30085
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3343710fbe4f1aba8c38e46a0a720f78944a1c10
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776925"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="4dcaf-102">ISymUnmanagedDocumentWriter::SetCheckSum メソッド</span><span class="sxs-lookup"><span data-stu-id="4dcaf-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="4dcaf-103">チェックサム情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="4dcaf-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dcaf-104">構文</span><span class="sxs-lookup"><span data-stu-id="4dcaf-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dcaf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4dcaf-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="4dcaf-106">[in]アルゴリズムの識別子を表す GUID。</span><span class="sxs-lookup"><span data-stu-id="4dcaf-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="4dcaf-107">[in]A`ULONG32`のサイズ (バイト単位) を示す、`checkSum`バッファー。</span><span class="sxs-lookup"><span data-stu-id="4dcaf-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="4dcaf-108">[in]チェックサム情報を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="4dcaf-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4dcaf-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="4dcaf-109">Return Value</span></span>  
 <span data-ttu-id="4dcaf-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="4dcaf-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dcaf-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="4dcaf-111">Requirements</span></span>  
 <span data-ttu-id="4dcaf-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4dcaf-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dcaf-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="4dcaf-113">See also</span></span>

- [<span data-ttu-id="4dcaf-114">ISymUnmanagedDocumentWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4dcaf-114">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
