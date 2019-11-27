---
title: ICeeGen::GetString メソッド
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
ms.openlocfilehash: e81ef33f4fb684cce29aa9afb756451b1e5db896
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426161"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="6b338-102">ICeeGen::GetString メソッド</span><span class="sxs-lookup"><span data-stu-id="6b338-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="6b338-103">指定した相対仮想アドレスに格納されている文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="6b338-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="6b338-104">このメソッドは互換性のために残されています。使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6b338-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b338-105">構文</span><span class="sxs-lookup"><span data-stu-id="6b338-105">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in]  ULONG      RVA,   
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b338-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6b338-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="6b338-107">から返される文字列の相対仮想アドレス。</span><span class="sxs-lookup"><span data-stu-id="6b338-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="6b338-108">入出力返された文字列。</span><span class="sxs-lookup"><span data-stu-id="6b338-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b338-109">要件</span><span class="sxs-lookup"><span data-stu-id="6b338-109">Requirements</span></span>  
 <span data-ttu-id="6b338-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b338-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b338-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="6b338-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6b338-112">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b338-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6b338-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b338-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b338-114">参照</span><span class="sxs-lookup"><span data-stu-id="6b338-114">See also</span></span>

- [<span data-ttu-id="6b338-115">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6b338-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
