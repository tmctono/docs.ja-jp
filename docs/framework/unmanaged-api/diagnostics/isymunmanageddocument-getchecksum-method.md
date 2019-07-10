---
title: ISymUnmanagedDocument::GetCheckSum メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b34f985f199542612bcdb9b30ebae28649438e1b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776768"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="f083c-102">ISymUnmanagedDocument::GetCheckSum メソッド</span><span class="sxs-lookup"><span data-stu-id="f083c-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="f083c-103">チェックサムを取得します。</span><span class="sxs-lookup"><span data-stu-id="f083c-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f083c-104">構文</span><span class="sxs-lookup"><span data-stu-id="f083c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f083c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f083c-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="f083c-106">[in]によって提供されるバッファーの長さ、`data`パラメーター</span><span class="sxs-lookup"><span data-stu-id="f083c-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="f083c-107">[out]サイズとチェックサムをバイト単位の長さ。</span><span class="sxs-lookup"><span data-stu-id="f083c-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="f083c-108">[out]チェックサムを受け取るバッファー。</span><span class="sxs-lookup"><span data-stu-id="f083c-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f083c-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="f083c-109">Return Value</span></span>  
 <span data-ttu-id="f083c-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、エラー コード。</span><span class="sxs-lookup"><span data-stu-id="f083c-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f083c-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f083c-111">See also</span></span>

- [<span data-ttu-id="f083c-112">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f083c-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
