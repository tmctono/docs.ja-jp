---
title: ISymUnmanagedDocument::GetLanguage メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguage
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguage
helpviewer_keywords:
- ISymUnmanagedDocument::GetLanguage method [.NET Framework debugging]
- GetLanguage method [.NET Framework debugging]
ms.assetid: c6639418-e9f2-4a99-8ce2-ec9876e0bc79
topic_type:
- apiref
ms.openlocfilehash: cea18fefa2d356cbb5857db5133b1086c38ac6ff
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449178"
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="5a0ea-102">ISymUnmanagedDocument::GetLanguage メソッド</span><span class="sxs-lookup"><span data-stu-id="5a0ea-102">ISymUnmanagedDocument::GetLanguage Method</span></span>
<span data-ttu-id="5a0ea-103">このドキュメントの言語識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="5a0ea-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a0ea-104">構文</span><span class="sxs-lookup"><span data-stu-id="5a0ea-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a0ea-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a0ea-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="5a0ea-106">入出力言語識別子を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5a0ea-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a0ea-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="5a0ea-107">Return Value</span></span>  
 <span data-ttu-id="5a0ea-108">メソッドが成功した場合は S_OK します。</span><span class="sxs-lookup"><span data-stu-id="5a0ea-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a0ea-109">参照</span><span class="sxs-lookup"><span data-stu-id="5a0ea-109">See also</span></span>

- [<span data-ttu-id="5a0ea-110">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a0ea-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
