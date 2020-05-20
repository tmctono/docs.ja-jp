---
title: ISymUnmanagedMethod::GetOffset メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetOffset
helpviewer_keywords:
- GetOffset method, ISymUnmanagedMethod interface [.NET Framework debugging]
- ISymUnmanagedMethod::GetOffset method [.NET Framework debugging]
ms.assetid: 8bf3cb62-89bf-4159-ad53-de606aba89e8
topic_type:
- apiref
ms.openlocfilehash: 358f3d3d7c231a2baa9d2c467935ba3a5867e36b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614475"
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="a44eb-102">ISymUnmanagedMethod::GetOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="a44eb-102">ISymUnmanagedMethod::GetOffset Method</span></span>
<span data-ttu-id="a44eb-103">ドキュメント内の指定された位置に対応する、このメソッド内のオフセットを返します。</span><span class="sxs-lookup"><span data-stu-id="a44eb-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a44eb-104">構文</span><span class="sxs-lookup"><span data-stu-id="a44eb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a44eb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a44eb-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="a44eb-106">からオフセットが要求されるドキュメントへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a44eb-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="a44eb-107">からオフセットの要求対象となるドキュメント行。</span><span class="sxs-lookup"><span data-stu-id="a44eb-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="a44eb-108">からオフセットが要求されるドキュメント列。</span><span class="sxs-lookup"><span data-stu-id="a44eb-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="a44eb-109">入出力オフセットを受け取るへのポインター `ULONG32` 。</span><span class="sxs-lookup"><span data-stu-id="a44eb-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a44eb-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="a44eb-110">Return Value</span></span>  
 <span data-ttu-id="a44eb-111">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="a44eb-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a44eb-112">要件</span><span class="sxs-lookup"><span data-stu-id="a44eb-112">Requirements</span></span>  
 <span data-ttu-id="a44eb-113">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="a44eb-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a44eb-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="a44eb-114">See also</span></span>

- [<span data-ttu-id="a44eb-115">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a44eb-115">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
