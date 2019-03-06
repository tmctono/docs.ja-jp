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
ms.openlocfilehash: 80cda4c31ca78e0350639df809ec1e9f1dcbbaea
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498251"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="1ce41-102">ISymUnmanagedDocument::GetCheckSum メソッド</span><span class="sxs-lookup"><span data-stu-id="1ce41-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="1ce41-103">チェックサムを取得します。</span><span class="sxs-lookup"><span data-stu-id="1ce41-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ce41-104">構文</span><span class="sxs-lookup"><span data-stu-id="1ce41-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ce41-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1ce41-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="1ce41-106">[in]によって提供されるバッファーの長さ、`data`パラメーター</span><span class="sxs-lookup"><span data-stu-id="1ce41-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="1ce41-107">[out]サイズとチェックサムをバイト単位の長さ。</span><span class="sxs-lookup"><span data-stu-id="1ce41-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="1ce41-108">[out]チェックサムを受け取るバッファー。</span><span class="sxs-lookup"><span data-stu-id="1ce41-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ce41-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="1ce41-109">Return Value</span></span>  
 <span data-ttu-id="1ce41-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、エラー コード。</span><span class="sxs-lookup"><span data-stu-id="1ce41-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ce41-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ce41-111">See also</span></span>
- [<span data-ttu-id="1ce41-112">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1ce41-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
