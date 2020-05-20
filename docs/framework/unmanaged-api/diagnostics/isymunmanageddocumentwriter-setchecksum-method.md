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
ms.openlocfilehash: 06a331e24622e0a155d974ca869818a6532baa1f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615541"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="5522f-102">ISymUnmanagedDocumentWriter::SetCheckSum メソッド</span><span class="sxs-lookup"><span data-stu-id="5522f-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="5522f-103">チェックサム情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="5522f-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5522f-104">構文</span><span class="sxs-lookup"><span data-stu-id="5522f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5522f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5522f-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="5522f-106">からアルゴリズム識別子を表す GUID。</span><span class="sxs-lookup"><span data-stu-id="5522f-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="5522f-107">から`ULONG32`バッファーのサイズ (バイト単位) を示す `checkSum` 。</span><span class="sxs-lookup"><span data-stu-id="5522f-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="5522f-108">からチェックサム情報を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="5522f-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5522f-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="5522f-109">Return Value</span></span>  
 <span data-ttu-id="5522f-110">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="5522f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5522f-111">要件</span><span class="sxs-lookup"><span data-stu-id="5522f-111">Requirements</span></span>  
 <span data-ttu-id="5522f-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="5522f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5522f-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="5522f-113">See also</span></span>

- [<span data-ttu-id="5522f-114">ISymUnmanagedDocumentWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5522f-114">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)
