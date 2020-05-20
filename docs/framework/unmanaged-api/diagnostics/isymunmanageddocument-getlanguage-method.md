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
ms.openlocfilehash: 084f3ae12d906f5e80fdb86e65b09d2371fd246b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614592"
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="82972-102">ISymUnmanagedDocument::GetLanguage メソッド</span><span class="sxs-lookup"><span data-stu-id="82972-102">ISymUnmanagedDocument::GetLanguage Method</span></span>
<span data-ttu-id="82972-103">このドキュメントの言語識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="82972-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82972-104">構文</span><span class="sxs-lookup"><span data-stu-id="82972-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82972-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82972-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="82972-106">入出力言語識別子を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="82972-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82972-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="82972-107">Return Value</span></span>  
 <span data-ttu-id="82972-108">メソッドが成功した場合は S_OK します。</span><span class="sxs-lookup"><span data-stu-id="82972-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82972-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="82972-109">See also</span></span>

- [<span data-ttu-id="82972-110">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="82972-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
