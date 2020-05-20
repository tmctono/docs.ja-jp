---
title: ISymUnmanagedReader::GetMethodVersion メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
ms.openlocfilehash: 8ee4c1bffccb44d15fa53eb3d4d6c0fcdc3e7697
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614969"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="64980-102">ISymUnmanagedReader::GetMethodVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="64980-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="64980-103">メソッドのバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="64980-103">Gets the method version.</span></span> <span data-ttu-id="64980-104">メソッドのバージョンは1から始まり、メソッドが再コンパイルされるたびにインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="64980-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="64980-105">再コンパイルは、メソッドを変更せずに発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64980-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64980-106">構文</span><span class="sxs-lookup"><span data-stu-id="64980-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64980-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="64980-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="64980-108">からバージョンを取得するメソッド。</span><span class="sxs-lookup"><span data-stu-id="64980-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="64980-109">入出力メソッドのバージョンを受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="64980-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64980-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="64980-110">Return Value</span></span>  
 <span data-ttu-id="64980-111">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="64980-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64980-112">要件</span><span class="sxs-lookup"><span data-stu-id="64980-112">Requirements</span></span>  
 <span data-ttu-id="64980-113">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="64980-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64980-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="64980-114">See also</span></span>

- [<span data-ttu-id="64980-115">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="64980-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
