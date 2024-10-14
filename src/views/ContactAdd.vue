<template>
    <div class="page">
        <h4>Thêm mới liên hệ</h4>
        <ContactForm :contact="contact" @submit:contact="insertContact"></ContactForm>
    </div>
</template>

<script>
import ContactForm from '@/components/ContactForm.vue';
import contactService from '@/services/contact.service';
export default {
    components: {
        ContactForm,
    },
    data() {
        return {
            contact: {
                name: null,
                emai: null,
                address: null,
                phone: null,
                favorite: false,
            },
        }
    },
    methods: {
        async insertContact(data) {
            try {
                await contactService.create(data);
                alert('Liên hệ đã được cập nhật thành công.');
                this.$router.push({ name: "contactbook" });
            } catch (error) {
                console.error(error);
            }
        }
    }
}

</script>