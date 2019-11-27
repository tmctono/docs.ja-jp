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
ms.openlocfilehash: 889fd4ec3332cbe80a035e13a5145421dc0ed5a9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448896"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="4ca11-102">ISymUnmanagedMethod::GetSequencePointCount メソッド</span><span class="sxs-lookup"><span data-stu-id="4ca11-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>
<span data-ttu-id="4ca11-103">このメソッド内のシーケンスポイントの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="4ca11-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ca11-104">構文</span><span class="sxs-lookup"><span data-stu-id="4ca11-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ca11-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4ca11-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4ca11-106">入出力シーケンスポイントを格納するために必要なバッファーのサイズを受け取る `ULONG32` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="4ca11-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ca11-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="4ca11-107">Return Value</span></span>  
 <span data-ttu-id="4ca11-108">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="4ca11-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ca11-109">要件</span><span class="sxs-lookup"><span data-stu-id="4ca11-109">Requirements</span></span>  
 <span data-ttu-id="4ca11-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="4ca11-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca11-111">参照</span><span class="sxs-lookup"><span data-stu-id="4ca11-111">See also</span></span>

- [<span data-ttu-id="4ca11-112">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ca11-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
