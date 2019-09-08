---
title: StrongNameSignatureVerification 関数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerification
helpviewer_keywords:
- StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8943df861b1bff2b28c68d0233fc336d1b5d4579
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798949"
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="4f72e-102">StrongNameSignatureVerification 関数</span><span class="sxs-lookup"><span data-stu-id="4f72e-102">StrongNameSignatureVerification Function</span></span>
<span data-ttu-id="4f72e-103">指定したパスにあるアセンブリ マニフェストに厳密な名前の署名が含まれるかどうかを示す値が取得されます。これは指定したフラグに従って確認されます。</span><span class="sxs-lookup"><span data-stu-id="4f72e-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="4f72e-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="4f72e-104">This function has been deprecated.</span></span> <span data-ttu-id="4f72e-105">代わりに[ICLRStrongName:: StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="4f72e-105">Use the [ICLRStrongName::StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f72e-106">構文</span><span class="sxs-lookup"><span data-stu-id="4f72e-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f72e-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4f72e-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="4f72e-108">から検証するアセンブリの移植可能な実行可能ファイル (.dll または .exe) ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="4f72e-108">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="4f72e-109">から検証動作を変更するフラグ。</span><span class="sxs-lookup"><span data-stu-id="4f72e-109">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="4f72e-110">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4f72e-110">The following values are supported:</span></span>  
  
- <span data-ttu-id="4f72e-111">`SN_INFLAG_FORCE_VER`(0x00000001)-レジストリ設定を上書きする必要がある場合でも、検証を強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="4f72e-111">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="4f72e-112">`SN_INFLAG_INSTALL`(0x00000002)-マニフェストを初めて検証するときに指定します。</span><span class="sxs-lookup"><span data-stu-id="4f72e-112">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
- <span data-ttu-id="4f72e-113">`SN_INFLAG_ADMIN_ACCESS`(0x00000004)-キャッシュが管理者特権を持つユーザーのみにアクセスを許可することを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f72e-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="4f72e-114">`SN_INFLAG_USER_ACCESS`(0x00000008)-現在のユーザーのみがアセンブリにアクセスできるように指定します。</span><span class="sxs-lookup"><span data-stu-id="4f72e-114">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="4f72e-115">`SN_INFLAG_ALL_ACCESS`(0x00000010)-キャッシュがアクセス制限の保証を提供しないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f72e-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="4f72e-116">`SN_INFLAG_RUNTIME`(0x80000000)-内部デバッグ用に予約されています。</span><span class="sxs-lookup"><span data-stu-id="4f72e-116">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="4f72e-117">入出力厳密な名前の署名が検証されたかどうかを示すフラグ。</span><span class="sxs-lookup"><span data-stu-id="4f72e-117">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="4f72e-118">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4f72e-118">The following value is supported:</span></span>  
  
- <span data-ttu-id="4f72e-119">`SN_OUTFLAG_WAS_VERIFIED`(0x00000001)-この値は、レジストリ`false`設定によって検証が成功したことを指定するためにに設定されます。</span><span class="sxs-lookup"><span data-stu-id="4f72e-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f72e-120">戻り値</span><span class="sxs-lookup"><span data-stu-id="4f72e-120">Return Value</span></span>  
 <span data-ttu-id="4f72e-121">`true`検証が成功した場合は、それ以外`false`の場合は。</span><span class="sxs-lookup"><span data-stu-id="4f72e-121">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f72e-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="4f72e-122">Requirements</span></span>  
 <span data-ttu-id="4f72e-123">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f72e-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f72e-124">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="4f72e-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="4f72e-125">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="4f72e-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4f72e-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f72e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f72e-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f72e-127">See also</span></span>

- [<span data-ttu-id="4f72e-128">StrongNameSignatureVerification メソッド</span><span class="sxs-lookup"><span data-stu-id="4f72e-128">StrongNameSignatureVerification Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="4f72e-129">StrongNameSignatureVerificationEx メソッド</span><span class="sxs-lookup"><span data-stu-id="4f72e-129">StrongNameSignatureVerificationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="4f72e-130">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f72e-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
