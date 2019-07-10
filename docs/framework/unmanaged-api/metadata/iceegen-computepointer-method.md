---
title: ICeeGen::ComputePointer メソッド
ms.date: 03/30/2017
api_name:
- ICeeGen.ComputePointer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5741ba1b4564a703ff57b45c728bb9efac0bb35a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782005"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="72ddb-102">ICeeGen::ComputePointer メソッド</span><span class="sxs-lookup"><span data-stu-id="72ddb-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="72ddb-103">指定したコードのセクションのバッファーを決定します。</span><span class="sxs-lookup"><span data-stu-id="72ddb-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="72ddb-104">このメソッドは廃止され、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72ddb-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72ddb-105">構文</span><span class="sxs-lookup"><span data-stu-id="72ddb-105">Syntax</span></span>  
  
```cpp  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,   
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72ddb-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="72ddb-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="72ddb-107">[in]バッファーを返す対象のコード セクション。</span><span class="sxs-lookup"><span data-stu-id="72ddb-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="72ddb-108">[in]ポインターを取得する対象のメソッドの相対仮想アドレス。</span><span class="sxs-lookup"><span data-stu-id="72ddb-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="72ddb-109">[out]返されたバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="72ddb-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72ddb-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="72ddb-110">Requirements</span></span>  
 <span data-ttu-id="72ddb-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="72ddb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72ddb-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="72ddb-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="72ddb-113">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="72ddb-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="72ddb-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72ddb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72ddb-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="72ddb-115">See also</span></span>

- [<span data-ttu-id="72ddb-116">ICeeGen インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72ddb-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
