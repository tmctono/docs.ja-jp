---
title: ISymUnmanagedMethod::GetSequencePointCount メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePointCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePointCount
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePointCount method [.NET Framework debugging]
- GetSequencePointCount method [.NET Framework debugging]
ms.assetid: 836133e8-6108-4b9b-b0a9-bce4e08dccda
topic_type:
- apiref
ms.openlocfilehash: a44f81deb2d57b49f1fd0650fa52c06383210352
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614436"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="f0268-102">ISymUnmanagedMethod::GetSequencePointCount メソッド</span><span class="sxs-lookup"><span data-stu-id="f0268-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>
<span data-ttu-id="f0268-103">このメソッド内のシーケンスポイントの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="f0268-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0268-104">構文</span><span class="sxs-lookup"><span data-stu-id="f0268-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0268-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f0268-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="f0268-106">入出力`ULONG32`シーケンスポイントを格納するために必要なバッファーのサイズを受け取るへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f0268-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0268-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="f0268-107">Return Value</span></span>  
 <span data-ttu-id="f0268-108">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0268-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0268-109">要件</span><span class="sxs-lookup"><span data-stu-id="f0268-109">Requirements</span></span>  
 <span data-ttu-id="f0268-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="f0268-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0268-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0268-111">See also</span></span>

- [<span data-ttu-id="f0268-112">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f0268-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
