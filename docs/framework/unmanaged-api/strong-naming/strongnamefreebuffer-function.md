---
title: StrongNameFreeBuffer 関数
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
ms.openlocfilehash: 11821acbeeb04ae09464eb0e032b9bf387914168
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095051"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="75f7d-102">StrongNameFreeBuffer 関数</span><span class="sxs-lookup"><span data-stu-id="75f7d-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="75f7d-103">[StrongNameGetPublicKey](strongnamegetpublickey-function.md)、[StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md)、または[StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md) などの厳密な名前の関数に対する前の呼び出しで割り当てられたメモリが解放されます。</span><span class="sxs-lookup"><span data-stu-id="75f7d-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="75f7d-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="75f7d-104">This function has been deprecated.</span></span> <span data-ttu-id="75f7d-105">代わりに[ICLRStrongName:: StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="75f7d-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75f7d-106">構文</span><span class="sxs-lookup"><span data-stu-id="75f7d-106">Syntax</span></span>  
  
```cpp  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75f7d-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="75f7d-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="75f7d-108">から解放するメモリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="75f7d-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75f7d-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="75f7d-109">Requirements</span></span>  
 <span data-ttu-id="75f7d-110">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75f7d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75f7d-111">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="75f7d-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="75f7d-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="75f7d-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="75f7d-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75f7d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75f7d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="75f7d-114">See also</span></span>

- [<span data-ttu-id="75f7d-115">StrongNameFreeBuffer メソッド</span><span class="sxs-lookup"><span data-stu-id="75f7d-115">StrongNameFreeBuffer Method</span></span>](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="75f7d-116">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="75f7d-116">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
