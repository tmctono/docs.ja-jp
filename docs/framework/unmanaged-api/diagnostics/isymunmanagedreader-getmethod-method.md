---
title: ISymUnmanagedReader::GetMethod メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedReader interface [.NET Framework debugging]
- ISymUnmanagedReader::GetMethod method [.NET Framework debugging]
ms.assetid: ae6cfb29-bc2c-4606-af86-1d32ebd31020
topic_type:
- apiref
ms.openlocfilehash: 864acb07797676c825afe62321b0d65e37938fa6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615008"
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="59e85-102">ISymUnmanagedReader::GetMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="59e85-102">ISymUnmanagedReader::GetMethod Method</span></span>
<span data-ttu-id="59e85-103">メソッドトークンを指定して、シンボルリーダーメソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="59e85-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59e85-104">構文</span><span class="sxs-lookup"><span data-stu-id="59e85-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59e85-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="59e85-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="59e85-106">からメソッドトークン。</span><span class="sxs-lookup"><span data-stu-id="59e85-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="59e85-107">入出力返されたインターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="59e85-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59e85-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="59e85-108">Return Value</span></span>  
 <span data-ttu-id="59e85-109">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="59e85-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59e85-110">要件</span><span class="sxs-lookup"><span data-stu-id="59e85-110">Requirements</span></span>  
 <span data-ttu-id="59e85-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="59e85-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59e85-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="59e85-112">See also</span></span>

- [<span data-ttu-id="59e85-113">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="59e85-113">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
