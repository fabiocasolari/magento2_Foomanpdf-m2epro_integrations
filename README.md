# magento2_Foomanpdf-m2epro_integrations

vendor/fooman/pdfcustomiser-implementation-m2/src/Block/AbstractSalesDocument.php

add after    $block->setTemplate($this->templateFileDecider->pick($this->getDesign(), 'shipping'));

        if(array_key_exists('channel_order_id', $this->getOrder()->getPayment()->getAdditionalInformation())) {
            $m2epro_description = 'Ordine ';
            $m2epro_description .= $this->getOrder()->getPayment()->getAdditionalInformation()['component_mode'];
            $m2epro_description .= ': ';
            $m2epro_description .= $this->getOrder()->getPayment()->getAdditionalInformation()['channel_order_id'];
            $block->setShippingDescription($m2epro_description);
        } else {
            $block->setShippingDescription($this->getOrder()->getShippingDescription());
        }
