---
title: ISymUnmanagedDocument::GetSourceLength メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2717a279abf7fb1b704a769d54654d97949cc0a2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136904"
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="24b4e-102">ISymUnmanagedDocument::GetSourceLength メソッド</span><span class="sxs-lookup"><span data-stu-id="24b4e-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>
<span data-ttu-id="24b4e-103">埋め込まれたソースの長さをバイト数で取得します。</span><span class="sxs-lookup"><span data-stu-id="24b4e-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24b4e-104">構文</span><span class="sxs-lookup"><span data-stu-id="24b4e-104">Syntax</span></span>  
  
```  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24b4e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="24b4e-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="24b4e-106">[out]埋め込みのソースの長さをバイト単位で示す変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="24b4e-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="24b4e-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="24b4e-107">Return Value</span></span>  
 <span data-ttu-id="24b4e-108">メソッドが成功した場合は s_ok を返します。</span><span class="sxs-lookup"><span data-stu-id="24b4e-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24b4e-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="24b4e-109">See also</span></span>

- [<span data-ttu-id="24b4e-110">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="24b4e-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
