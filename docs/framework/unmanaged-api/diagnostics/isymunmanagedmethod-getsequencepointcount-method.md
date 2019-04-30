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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9eac17ec9599caba88ddaa73d28abcae538a4d19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939582"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="88111-102">ISymUnmanagedMethod::GetSequencePointCount メソッド</span><span class="sxs-lookup"><span data-stu-id="88111-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>
<span data-ttu-id="88111-103">このメソッド内のシーケンス ポイントの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="88111-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88111-104">構文</span><span class="sxs-lookup"><span data-stu-id="88111-104">Syntax</span></span>  
  
```  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88111-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="88111-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="88111-106">[out]ポインター、`ULONG32`シーケンス ポイントの格納に必要なバッファーのサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="88111-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88111-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="88111-107">Return Value</span></span>  
 <span data-ttu-id="88111-108">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="88111-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88111-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="88111-109">Requirements</span></span>  
 <span data-ttu-id="88111-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="88111-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88111-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="88111-111">See also</span></span>

- [<span data-ttu-id="88111-112">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="88111-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
